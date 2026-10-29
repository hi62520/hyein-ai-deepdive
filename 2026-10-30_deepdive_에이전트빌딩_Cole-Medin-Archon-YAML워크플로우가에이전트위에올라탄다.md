---
date: 2026-10-30
category: 에이전트빌딩
subject: Cole Medin — Archon, YAML 워크플로우가 에이전트 위에 올라탄다
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱 이슈→PR 흐름을 Archon YAML 5단계(plan→implement→test→approve→PR)로 초안 작성
---

# Cole Medin — Archon, YAML 워크플로우가 에이전트 위에 올라탄다

## 누구인가

Cole Medin(@coleam00)은 AI 에이전트 빌딩 분야에서 가장 빠르게 성장한 실무 YouTuber입니다. 2024년 초까지만 해도 무명에 가까웠던 그의 채널은 2025년 말 구독자 10만 명을 넘은 뒤, 2026년 중반에는 약 22만 명을 돌파했습니다. 그는 현재 Dynamous의 창업자이자 오픈소스 도구 Archon의 메인테이너입니다. 그의 콘텐츠는 "에이전트를 실제 프로덕션에서 어떻게 굴리는가"에 집중합니다. Pydantic AI, LangGraph, MCP 통합, 로컬 LLM 배포까지 모두 다루지만, 2026년의 핵심 프로젝트는 단연 Archon입니다. GitHub에서만 스타 23,800개, 포크 3,500개를 기록한 이 도구는 에이전트 코딩의 결정론적(deterministic) 실행을 가능하게 합니다.

## 무엇이 특별한가

### 1. "에이전트는 판단만, 프로세스는 YAML이 고정한다"

Archon의 핵심 철학은 한 줄로 요약됩니다: **워크플로우를 YAML로 고정하고, LLM에게는 각 단계 안의 판단만 맡긴다.** 기존 에이전트 프레임워크의 문제는 에이전트가 '무엇을 할지'와 '어떻게 할지'를 동시에 결정한다는 것입니다. Archon은 이를 분리합니다. 계획(plan) → 구현(implement) → 테스트(test) → 승인(approve) → PR 생성이라는 순서는 YAML이 강제하고, 에이전트(Claude Code, Codex CLI)는 각 단계에서 '이 맥락에서 무엇을 쓸 것인가'만 결정합니다. 결과적으로 같은 이슈를 10번 돌려도 같은 흐름이 나옵니다.

### 2. "Human on the loop, not in it"

Archon의 공식 GitHub에 적힌 이 문구는 Cole Medin이 에이전트 자동화를 바라보는 시각을 압축합니다. 큐(queue)가 이슈를 받아 자동으로 처리하고, 사람에게 알림이 오는 것은 에이전트가 '판단 불가' 표시를 올린 순간뿐입니다. `archon workflow attention` 명령 하나로 터미널에서 응답하고 다시 위임합니다. 대표님의 비서앱·ERP 맥락에서 말하면, 주문 접수 → 재고 확인 → 견적 발행까지는 흐르다가, "재고 부족 대체품 선택" 같은 진짜 판단만 올라오는 구조입니다.

### 3. 69%의 PR이 에이전트 손에서 나왔다

2026년 10월 1일~19일, Archon 저장소 자체에 병합된 PR 524개 중 363개(약 69%)가 Archon 실행으로 자동 생성됐습니다. 이것이 단순한 벤치마크가 아닌 이유는 저장소 자체의 개발 사이클에 Archon을 돌렸기 때문입니다. 자기 자신을 만드는 데 자기 자신을 사용하는 구조—이것이 Cole Medin이 스스로 '팩토리 빌더(factory builder)'라고 부르는 이유입니다.

### 4. 2026년 4월, Python 코드베이스 전부 폐기하고 TypeScript로 재작성

2026년 4월 7일, Cole Medin은 1만 스타를 넘긴 Python + Pydantic AI 기반의 Archon 원본 코드를 전부 아카이빙하고 TypeScript로 재작성했습니다. 이유는 하나입니다: 기존 코드는 에이전트-빌더-에이전트(AI가 AI를 만드는) 구조로 설계됐는데, "결국 에이전트의 판단이 너무 많이 들어가 재현 불가한 결과가 나온다"는 것이었습니다. 새 버전은 워크플로우 엔진으로 방향을 완전히 틀었습니다.

### 5. Archon은 에이전트가 아니라 에이전트의 감독관(harness)이다

Archon은 코드를 직접 쓰지 않습니다. Claude Code나 Codex CLI를 각자의 CLI/SDK로 실행하고, 그 실행을 YAML 그래프 위에서 조율합니다. 각 노드는 에이전트 프롬프트, bash 명령, 반복 루프, 사람 대기(wait), 하위 워크플로우 중 하나입니다. `.archon/workflows/` 폴더에 YAML을 두고 `archon workflow run sdlc "이슈 #42 처리해줘"`만 치면 됩니다. 비용 추적, 이벤트 로그, 대화 기록이 모두 SQLite(또는 PostgreSQL)에 자동 저장됩니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱의 이슈→PR 흐름을 Archon YAML 5단계로 초안 작성. `plan → implement → loop_until_test_pass → wait_approval → create_pr` 구조를 텍스트로 그려보기. 실제 설치 없이 구조 설계만 해도 ERP 자동화 흐름에 즉시 적용됩니다.

**이번 주 1-2시간 (mid)**: Archon을 실제 설치하고(`curl` 한 줄), 와당탕 레포에 `.archon/workflows/simple-fix.yaml`을 작성해봅니다. 단계는 3개면 충분: plan → implement → pr. Claude Code가 이미 설치돼 있으니 즉시 실행 가능합니다. 아래 스니펫 참고:

```yaml
# .archon/workflows/simple-fix.yaml
name: simple-fix
steps:
  - id: plan
    type: agent
    prompt: "이슈 내용을 분석하고 변경 파일 목록을 작성해."
  - id: implement
    type: agent
    prompt: "plan 결과를 바탕으로 코드를 수정해. 테스트 통과할 때까지 반복."
    loop:
      until: "tests_pass"
      max: 5
  - id: pr
    type: agent
    prompt: "변경 사항을 커밋하고 PR을 열어."
```

**이번 달 실험 (macro)**: 와당탕 ERP의 반복 업무(주간 리포트 생성, 클라이언트 견적 초안 작성, 재고 정산 알림) 중 하나를 Archon YAML로 정의하고 2주간 실제 운영. 측정 지표: 처리 시간 단축율(분), 사람 개입 횟수(attention 알림 발생 빈도).

## 한국 솔로 운영자 맥락에서 주의

**1. Archon은 개발 워크플로우에 최적화돼 있습니다.** 현재 sdlc 팩은 이슈→PR 흐름입니다. 영업·고객 응대·콘텐츠 발행 같은 비개발 업무에 바로 적용하려면 커스텀 워크플로우를 직접 설계해야 합니다. Cole Medin의 영상은 대부분 개발자 독자 기준이므로, 와당탕 맥락에서는 "프로세스 고정" 개념만 빌려오고 실행 도구는 n8n이나 비서앱 내부 큐로 대체하는 것도 유효합니다.

**2. 23K 스타는 커뮤니티 관심이지, 프로덕션 검증이 아닙니다.** 2026년 4월 대규모 재작성 이후 아직 1년이 안 됐습니다. TypeScript 재작성 버전은 빠르게 발전 중이지만 API 변경도 잦습니다. 중요 업무에 붙이기 전에 사이드 프로젝트에서 먼저 패턴을 익히는 편이 안전합니다.

## 더 깊이 보려면
- [Archon GitHub (coleam00)](https://github.com/coleam00/archon)
- [Cole Medin YouTube (@ColeMedin)](https://www.youtube.com/@ColeMedin)
- [Cole Medin GitHub (coleam00)](https://github.com/coleam00)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "에이전트가 이슈를 받아 PR까지 냈는데, 왜 매번 과정이 달라지지?" — 재현 불가능한 에이전트 결과의 고통.
- **숫자**: 2026년 10월 19일간 Archon 저장소에 병합된 PR의 69%(524개 중 363개)가 에이전트 자동 생성. GitHub Stars 23,800개.
- **삽질**: Cole Medin 본인이 Python + Pydantic AI 버전(1만 스타 이상)을 통째로 폐기하고 TypeScript로 다시 짠 이유 — "에이전트에게 판단을 너무 많이 맡겼더니 재현이 안 됐다."
- **훅**: "AI 에이전트가 코드를 짜는 게 아니라, YAML이 에이전트를 부려먹는 시대입니다."
