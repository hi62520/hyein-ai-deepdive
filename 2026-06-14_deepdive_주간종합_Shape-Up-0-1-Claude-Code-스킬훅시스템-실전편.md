---
date: 2026-06-14
category: 주간종합
subject: Shape Up 0-1 — Claude Code 스킬·훅 시스템으로 코드 없이 제품을 설계하는 법
tags: [AI탐구, deepdive]
starred: false
micro_action: rjs/shaping-skills를 클론해 비서앱의 다음 기능에 `/shaping` 스킬을 실행하고, 생성된 Requirements 목록에서 Rabbit Hole 항목 1개 제거하기
---

# Shape Up 0-1 — Claude Code 스킬·훅 시스템으로 코드 없이 제품을 설계하는 법

## 이번 주 재조명 맥락

6월 11일 첫 번째 Deep Dive에서는 Shape Up의 개념(Appetite, 6주 사이클, Circuit Breaker)과 Ryan Singer가 Claude Code로 실험 중이라는 사실을 다뤘습니다. 그런데 그 이후 Singer의 X 타임라인에는 개념이 아닌 **실제 워크플로우 코드**가 올라오고 있습니다. 오늘은 그 구체적 내용, 즉 `rjs/shaping-skills` 레포의 작동 원리와 "0-1 shaping"이라는 새 개념, 그리고 Skills와 Hooks를 어떻게 조합하는지를 대표님이 내일 당장 실행할 수 있는 수준으로 분해합니다.

## 무엇이 달라졌나: "1-N"에서 "0-1"로

6월 11일 첫 Deep Dive에서 소개한 Claude Code × Shape Up 실험은 주로 **기존 코드베이스 탐색**(도메인 언어 혼동 해결, seam 찾기)에 집중했습니다. Singer가 2026년 들어 공개하기 시작한 것은 차원이 다릅니다. 이름하여 **"Shaping 0-1 with Claude Code"**입니다.

**1-N shaping**은 이미 돌아가는 코드가 있을 때, 새 기능을 그 위에 올리는 작업입니다. Claude Code가 코드베이스를 스캔해 기존 affordance를 매핑합니다. 반면 **0-1 shaping**은 코드가 없습니다. 머릿속의 문제 서술만 있는 상태에서 Claude Code가 다음을 순서대로 수행합니다:

1. **Problem/Outcome 추출**: "사용자가 겪는 고통은 무엇인가, 해결되면 무엇이 달라지는가"
2. **Requirements 초안**: `R1`, `R2`, `R3`… 형태로 넘버링된 요구사항 목록
3. **Initial Shape 스케치**: breadboard 형태의 Places–Affordances–Wiring 테이블
4. **Rabbit Holes 식별**: 범위를 초과할 수 있는 위험 구간 명시

> "I'm finding skills are effective for how to do things, but not good at enforcing things. Eg 'always do this before that.' So I combined the shaping skills with a hook that gives Claude a checklist whenever it modifies a shaping doc."  
> — Ryan Singer, X(@rjs) 2026년 6월

핵심 통찰: **Skills는 방법을 알려주고, Hooks는 절차를 강제합니다.**

## breadboarding 스킬의 실제 출력 구조

`rjs/shaping-skills` 레포(현재 ★1.4k, 포크 85개)의 `/breadboarding` 스킬이 만드는 산출물은 네 가지 표입니다.

| 산출물 | 설명 |
|---|---|
| **Places Table** | 사용자가 들어가는 맥락 공간. "이 뒤에 있는 것과 상호작용할 수 없으면 별개의 Place" |
| **UI Affordances** | 버튼·입력·표시. 고유 ID `U1`, `U2`… |
| **Code Affordances** | 메서드·스토어·구독. 고유 ID `N1`, `N2`… |
| **Data Stores** | 영구 상태. `S1`, `S2`… |

그리고 각 affordance에는 두 가지 관계가 붙습니다:
- **Wires Out**: 이것이 무엇을 트리거하는가 (제어 흐름)
- **Returns To**: 출력이 어디로 흘러가는가 (데이터 흐름)

마지막으로 **Vertical Slices**를 최대 9개, 슬라이스당 최대 15개 affordance 기준으로 잘라냅니다. 각 슬라이스는 독립적으로 데모 가능한 가시적 UI를 갖춰야 합니다.

이것이 왜 강력한가? 솔로 운영자 입장에서 Claude Code에게 "이 기능 만들어줘"라고 하면 Claude는 잘못된 abstraction을 만들거나, scope를 무한정 키웁니다. 0-1 shaping은 **Claude가 코드를 건드리기 전에 scope를 고정**시키는 선행 단계입니다.

## Skills + Hooks 조합: 절차를 강제하는 ripple-check

Singer가 최근 발견한 또 다른 한계: Skills는 "어떻게 하는가"를 훌륭하게 가이드하지만, "반드시 A 다음에 B를 하라"는 순서를 강제하지 못합니다. 해결책으로 그는 **ripple-check hook**을 추가했습니다.

작동 방식은 이렇습니다. shaping doc을 수정할 때마다 Claude가 자동으로 체크리스트를 받습니다:

```
shaping doc 수정 감지 시 Claude 체크리스트:
□ Affordance 테이블이 변경 사항을 반영했는가?
□ Fit Analysis(요구사항 충족 검토)가 업데이트됐는가?
□ Work Streams(슬라이스 할당)에 영향이 있는가?
□ Rabbit Holes 목록에 새 위험이 추가됐는가?
```

이 훅이 없으면 Claude는 shaping doc의 한 섹션만 바꾸고 나머지 일관성을 놓칩니다. 훅이 있으면 파일 편집 이벤트마다 전체 문서의 정합성이 강제 검토됩니다.

Claude Code의 hooks 시스템(`~/.claude/settings.json`의 `hooks` 키)을 활용하면 대표님도 동일하게 구현할 수 있습니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**:  
`rjs/shaping-skills` 레포를 클론해 비서앱에서 "다음에 만들 기능 하나"를 `/shaping` 스킬로 0-1 shaping document로 변환합니다. 생성된 Requirements 목록(`R1`, `R2`…)에서 Rabbit Hole로 표시된 항목 1개를 제거해 scope를 줄이는 연습을 합니다. 이것이 frontier `micro_action`과 동일합니다.

```bash
# 설치 (한 번만)
git clone https://github.com/rjs/shaping-skills.git ~/shaping-skills
mkdir -p ~/.claude/skills
ln -sf ~/shaping-skills/shaping ~/.claude/skills/shaping
ln -sf ~/shaping-skills/breadboarding ~/.claude/skills/breadboarding
ln -sf ~/shaping-skills/framing-doc ~/.claude/skills/framing-doc

# Claude Code 프로젝트 디렉터리(비서앱)에서 실행
cd ~/my-secretary-app
# Claude Code 실행 후 채팅창에:
# /shaping 다음 기능: 대표님이 외근 중에 메모를 음성으로 남기면 자동으로 옵시디언 인박스에 들어가는 기능
```

**이번 주 1-2시간 (mid)**:  
ripple-check hook을 비서앱 프로젝트의 `.claude/settings.json`에 추가합니다. shaping doc 파일(`*.shaping.md`)을 수정할 때마다 Claude가 자동으로 일관성 체크를 수행하게 설정합니다.

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit|Write",
        "hooks": [
          {
            "type": "prompt",
            "prompt": "방금 수정한 파일이 *.shaping.md 파일이라면: (1) Affordance 테이블 업데이트 여부, (2) Rabbit Holes 목록 반영 여부, (3) Vertical Slices 영향도를 체크하고 보고하세요."
          }
        ]
      }
    ]
  }
}
```

**이번 달 실험 (macro)**:  
비서앱과 느린호밀 ERP 각각에서 다음 릴리즈 기능 하나씩을 0-1 shaping으로 시작합니다. 기존 방식(바로 코드 생성 지시)과 0-1 shaping 경유 방식을 비교해 다음 지표를 측정합니다:
- 첫 번째 작동 버전까지 경과 시간
- 사이클 중간에 scope가 추가된 횟수
- 완성도 체감 점수(5점 만점, 출시 직후 자기 평가)

## 한국 솔로 운영자 맥락에서 주의

**1. 스킬 설치 자체가 시간을 먹는 함정.**  
`rjs/shaping-skills`는 Shell 스크립트 기반으로 symlink 설치가 필요합니다. 설치 과정에서 "이것도 커스터마이즈해볼까"로 빠지면 30분 micro action이 반나절 야크 면도가 됩니다. 설치 후 첫 날은 기본값 그대로 사용하고, 커스터마이즈는 두 번째 사이클로 미루세요.

**2. 0-1 shaping은 '아이디어가 많을 때' 더 위험합니다.**  
솔로 운영자는 머릿속에 기능 아이디어가 넘칩니다. Claude가 Requirements를 뽑아내면 `R1`~`R12`까지 나올 수 있습니다. 이 중 이번 appetite(예: 이번 주 3시간) 안에 들어오는 것은 3~4개뿐입니다. **나머지를 삭제하는 결단**이 0-1 shaping의 실질 가치입니다. Claude의 breadboard가 완성된 느낌을 주면 scope가 맞는다는 착각이 생깁니다. 항상 "이것이 3시간 안에 데모 가능한가?"로 재확인하세요.

## 더 깊이 보려면

- [rjs/shaping-skills GitHub](https://github.com/rjs/shaping-skills) — 설치 가능한 실제 스킬 파일
- [Ryan Singer X (@rjs)](https://x.com/rjs) — Shaping 0-1 실험 실시간 공개
- [Shape Up 원문 무료](https://basecamp.com/shapeup) — breadboarding 챕터 필독

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "Claude Code에게 '이 기능 만들어줘'라고 했더니 만들긴 만들었는데, 내가 원한 게 아니었다. 요구사항을 먼저 합의했어야 했는데, 그 도구가 없었다."
- **숫자**: rjs/shaping-skills 공개 직후 ★1.4k, 포크 85개. Claude Code 생태계에서 product methodology 레포로는 이례적 반응. 브레드보드 슬라이스 기준: 최대 9슬라이스 × 최대 15 affordance = 135개 요소가 6주 사이클의 설계 한도.
- **삽질**: Singer의 발견: "Skills는 '어떻게'를 가르치지만 '항상 이 순서로'를 강제하지 못한다." 처음엔 스킬만으로 운영하다가 Claude가 shaping doc 한 섹션만 바꾸고 나머지와 불일치 상태를 만드는 버그를 겪음. Hooks를 추가해 ripple-check를 강제하면서 해결.
- **훅**: "Claude Code에 '기능 만들어줘'라고 말하기 전에 해야 할 단계가 있습니다. 그 단계를 건너뛰면 코드는 빠르게 나오지만, 다시 짜게 됩니다."
