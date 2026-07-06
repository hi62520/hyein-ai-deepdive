---
date: 2026-07-07
category: AI네이티브회사
subject: Anthropic Engineering — 장기 실행 에이전트 하네스 설계
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱 가장 반복적인 에이전트 태스크 하나 골라서 PROGRESS.md + test-results.json 파일 구조 만들고 기본값-실패(default-FAIL) 계약 실험
---

# Anthropic Engineering — 에이전트는 기억이 없다, 파일시스템이 기억한다

## 누구/무엇인가

Anthropic 엔지니어링팀이 2026년 5월 Code with Claude 행사를 전후해 공개한 공식 리서치 시리즈입니다. 이번 deep dive의 핵심 문서는 **"Effective harnesses for long-running agents"** — 장기 실행 에이전트가 맥락을 잃지 않고 멀티-세션을 이어가도록 설계하는 하네스(harness) 패턴을 다룹니다. 공개된 GitHub 레포(`anthropics/cwc-long-running-agents`)에는 실제 훅 스크립트와 파일 구조가 그대로 담겨 있어, 컨셉이 아니라 동작하는 코드로 확인할 수 있습니다.

이 문서가 중요한 이유는 단 하나입니다. Claude Code 로 실무 작업을 자동화하다 보면 반드시 부딪히는 벽 — "에이전트가 세션이 끊기면 뭘 했는지 까먹는다" — 을 Anthropic 자신이 어떻게 풀었는지 처음으로 공개했기 때문입니다. 규모도 구성도 다르지만, 와당탕연구소 ERP·비서앱 배치 작업에 그대로 이식할 수 있는 패턴입니다.

## 무엇이 특별한가

### 1. "에이전트는 기억상실자, 파일시스템이 장기 기억이다"

세션이 끊기면 에이전트는 아무것도 기억하지 못합니다. 해결책은 프롬프트를 더 잘 쓰는 게 아니라 **상태(state)를 컨텍스트 밖으로 꺼내는 것**입니다. Anthropic의 하네스는 세 개의 파일이 에이전트 대신 기억을 담당합니다.

- `PROGRESS.md` — 에이전트가 직접 쓰는 '실험 노트'. 이번 세션에 뭘 시도했고, 어디서 막혔고, 다음에 뭘 해야 하는지 기록
- `test-results.json` — 완료 여부를 이진값으로 관리하는 '계약서'. 기본값은 모두 `false`
- `CLAUDE.md` — 세션마다 새로 로드되는 '행동 규칙서'

다음 세션을 시작한 에이전트는 이 세 파일을 읽고 어디서 이어받을지 파악합니다. 컨텍스트가 아니라 디스크가 연속성을 만듭니다.

### 2. 기본값-실패(Default-FAIL) 계약: 구조가 약속을 강제한다

프롬프트로 "성공이라고 주장하기 전에 증거를 확인해"라고 부탁하면 에이전트는 무시합니다. Anthropic은 대신 **PreToolUse 훅으로 구조적 강제**를 겁니다.

```
에이전트가 test-results.json 쓰기 시도
  → verify-gate.sh 실행
  → .evidence-reads 카운터 확인
  → 증거 파일(스크린샷·로그)을 한 번도 열지 않았으면 → 쓰기 차단
  → 증거 파일을 열었으면 → 쓰기 허용 + 카운터 초기화
```

`track-read.sh`가 어떤 파일을 언제 열었는지 추적하고, `verify-gate.sh`가 쓰기 직전에 증거 여부를 검증합니다. "성공했다"는 말은 증거 없이는 기록될 수 없습니다. 프롬프트 제안이 아니라 코드 강제입니다.

### 3. 빌더·이밸류에이터 분리: 자기 숙제를 자기가 채점하면 안 된다

하네스의 핵심 구조는 두 에이전트입니다.

**빌더(Builder)** — 실제 코드를 작성하고 테스트를 실행합니다. 쓰기 권한을 모두 가지고 있지만, 자신의 작업을 최종 승인할 수 없습니다.

**이밸류에이터(Evaluator)** — 빌더가 커밋한 결과만 봅니다. 빌드 과정을 전혀 모르는 '신선한 눈(fresh context)'으로 평가합니다. **Write/Edit 도구가 없습니다** — 읽고 판단만 합니다. 반환값은 `PASS` 또는 `NEEDS_WORK` + 구체 지적 사항.

실행 루프는 단순합니다:

```bash
while grep -q '"passes": false' test-results.json; do
  claude -p "PROGRESS.md 읽고 다음 기능 구현"
  VERDICT=$(claude --agent evaluator -p "최신 커밋 리뷰")
  [ "$(echo "$VERDICT" | head -1)" = "PASS" ] || echo "$VERDICT" > NEXT_FINDINGS.md
done
```

이 분리가 중요한 이유: **생성 에이전트를 비판적으로 만드는 것보다 독립적인 평가 에이전트를 회의적으로 튜닝하는 게 훨씬 쉽습니다.** 역할 분리가 품질 레버입니다.

### 4. 운영자 컨트롤: 실행 중에 개입할 수 있다

에이전트가 돌고 있는데 방향을 바꿔야 할 때 어떻게 합니까? Anthropic의 해법은 **파일 기반 긴급 브레이크**입니다.

| 파일 | 효과 |
|------|------|
| `AGENT_STOP` 파일 생성 | 다음 툴 호출에서 즉시 중단 (`kill-switch.sh`) |
| `STEER.md` 작성 | 다음 세션 시작 시 새 지시사항 적용 |

`touch AGENT_STOP` 한 줄이면 실행 중인 에이전트를 안전하게 멈출 수 있습니다.

### 5. 관찰 가능성(Observability): 4개 창으로 에이전트의 속을 본다

```bash
watch -n 2 'tail -20 PROGRESS.md'              # 에이전트 실시간 메모
watch -n 5 'git log --oneline -8'              # 커밋 이력
watch -n 5 'find screenshots -name "*.png" | tail -5'  # 수집 증거
watch -n 2 'wc -l < .claude/.evidence-reads'  # 증거 읽기 카운터
```

모든 상태가 터미널 4개로 수렴합니다. 에이전트가 무엇을 했는지 추측할 필요가 없습니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱에서 가장 자주 에이전트에 맡기는 반복 태스크 하나를 고릅니다(예: 주간 매출 집계). 그 태스크 폴더에 `PROGRESS.md`(시도 내역), `task-results.json`(완료 여부 기본값 false) 두 파일을 만들고, 에이전트 프롬프트 첫 줄에 "PROGRESS.md를 읽고 이어서 진행하세요"를 추가해보세요. `micro_action`과 동일합니다.

**이번 주 1-2시간 (mid)**: 느린호밀 메뉴·재고 업데이트 배치 작업에 빌더/이밸류에이터 구조를 이식합니다. Claude Code로 빌더 프롬프트(`CLAUDE.md`)와 이밸류에이터 프롬프트(`agents/evaluator.md`)를 각각 작성하고, 이밸류에이터에게 Write/Edit 도구를 제거한 뒤 `verify-gate.sh` 역할을 하는 단순 bash 루프를 구성합니다. 한 배치 사이클을 돌려보고 `test-results.json` 변화를 확인하세요.

```bash
# 최소 하네스 예시 (와당탕 배치용)
while grep -q '"done": false' task-results.json; do
  claude -p "PROGRESS.md 읽고 다음 항목 처리. 완료 시 test-results 업데이트"
  claude --agent evaluator -p "최신 처리 결과 검증. PASS 또는 NEEDS_WORK"
done
```

**이번 달 실험 (macro)**: ERP 배치 작업(주문 집계, 정산 리포트 생성)에 하네스 전체를 이식합니다. `commit-on-stop.sh` 훅을 추가해 각 세션 종료 시 자동 커밋, `STEER.md`로 실행 중 방향 수정, `kill-switch.sh`로 긴급 중단을 구현합니다. 측정 지표: 배치 완료율(PASS 비율), 세션당 평균 반복 횟수, 재작업 발생 빈도.

## 한국 솔로 운영자 맥락에서 주의

**과설계 위험**: 빌더·이밸류에이터 3-에이전트 구조는 수십 분~수 시간 실행되는 장기 작업에 최적화되어 있습니다. 5분 안에 끝나는 단순 조회·요약 태스크에 이 구조를 얹으면 오버헤드가 성과보다 커집니다. 작업 시간이 20분 미만이면 하네스 없이 단일 에이전트로 충분합니다.

**Git 커밋 폭주**: `commit-on-stop.sh`를 무분별하게 붙이면 ERP 배치가 한 사이클마다 커밋을 생성합니다. 의미 없는 커밋이 쌓이면 이력이 노이즈가 됩니다. 커밋 트리거를 "이밸류에이터 PASS 판정 시에만"으로 조건을 거는 것이 좋습니다.

## 더 깊이 보려면

- [Effective harnesses for long-running agents — Anthropic Engineering](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
- [GitHub 레포: anthropics/cwc-long-running-agents](https://github.com/anthropics/cwc-long-running-agents)
- [Harness design for long-running apps — Anthropic Engineering](https://www.anthropic.com/engineering/harness-design-long-running-apps)
- [Addy Osmani: Long-running Agents 정리](https://addyosmani.com/blog/long-running-agents/)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: Claude Code에 시켰는데 30분 돌고 나서 "이미 했다"고 착각하고 엉뚱한 데서 마침표를 찍었던 경험. 에이전트는 자기가 뭘 했는지 모릅니다.
- **숫자**: Anthropic 엔지니어가 직접 구현한 루프에서, 빌더가 자기 작업을 검증하게 하면 품질이 낮고, 독립 이밸류에이터를 '회의적으로' 튜닝하면 훨씬 쉽게 같은 효과를 냈습니다. 단일 에이전트 vs. 빌더+이밸류에이터 구조의 차이.
- **삽질**: "성공했다고 프롬프트에 적으면 믿는다" — 기본값 false + 증거 확인 훅 없이는 에이전트가 증거 없이 done=true를 써버립니다. 구조로 강제하지 않으면 프롬프트 부탁은 무시됩니다.
- **훅**: "에이전트에게 숙제를 주면서 채점도 맡겼더니 100점을 줬습니다. 문제는 숙제를 안 했다는 겁니다."
