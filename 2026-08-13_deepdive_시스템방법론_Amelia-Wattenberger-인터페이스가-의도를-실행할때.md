---
date: 2026-08-13
category: 시스템방법론
subject: Amelia Wattenberger — 인터페이스가 의도를 실행할 때
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱의 채팅 입력창 옆에 "맥락 고정" 토글 하나 추가 — 에이전트에게 이 대화의 범위(오늘 업무만/전체 프로젝트)를 슬라이더나 체크박스로 명시적으로 전달하도록 UX 1개 설계
---

# Amelia Wattenberger — 인터페이스가 의도를 실행할 때

## 누구/무엇인가

Amelia Wattenberger는 데이터 시각화 엔지니어 출신의 AI 인터페이스 설계자입니다. 신경과학을 전공하고 8년간 데이터 집약적 대시보드를 구축했으며, 이후 5년간 GitHub의 미래 연구팀 'GitHub Next'에서 Principal Research Engineer로 근무했습니다. 거기서 그는 AI가 개발 워크플로에 녹아들 때 인터페이스가 어떻게 바뀌어야 하는지를 실험했습니다.

2026년 현재 두 역할을 겸하고 있습니다. 실리콘밸리 대표 벤처캐피털 Sutter Hill Ventures의 Partner로서 AI 스타트업을 지원하고, 동시에 Augment Code의 Product Lead로서 **Intent**라는 멀티에이전트 워크스페이스를 직접 빌딩하고 있습니다. 또한 Rosenfeld Media를 통해 *Sentient Design: Crafting Intelligent Interfaces with AI* 를 집필 중이며, 2026년 Designing with AI 컨퍼런스의 주요 연사로 초청받았습니다.

Wattenberger의 핵심 주장은 하나입니다. **"AI는 채팅창 안에 가두기에는 너무 강력하다."**

## 무엇이 특별한가

### 1. 2023년에 이미 챗봇의 실패를 예언했다

그가 wattenberger.com에 발행한 *"Why Chatbots Are Not the Future of Interfaces"*(2023)는 지금 돌아보면 선지자적 글입니다. 당시 ChatGPT 열풍의 절정이었음에도 그는 냉정하게 진단했습니다.

> *"The only clue users receive with a typical chat interface is that they should type characters into the textbox — and the interface looks the same as a Google search box, a login form, and a credit card field."*  
> (한국어 의역) "채팅창이 사용자에게 주는 유일한 힌트는 '여기에 글자를 입력하세요'뿐이다. 그 직사각형은 구글 검색창, 로그인 폼, 신용카드 입력란과 구분이 되지 않는다."

그가 지적한 문제는 세 가지였습니다. 첫째, **어포던스 부재** — 무엇을 물어봐야 할지, 어떻게 물어봐야 효과적인지 인터페이스가 전혀 알려주지 않는다. 둘째, **학습 부담의 민주화 실패** — "어떤 프롬프트가 잘 되는지 배우는 부담이 모든 개별 사용자에게 전가된다." 셋째, **시각화의 빈곤** — "텍스트는 LLM 출력물 대부분에 대해 최적의 데이터 시각화가 아니다." 그는 슬라이더, 체크박스, diff 뷰 같은 컨텍스트 컨트롤을 인터페이스에 직접 내장하는 대안을 제시했습니다.

### 2. 플로 스테이트(Flow State)를 지키는 설계

그가 GitHub Next에서 5년간 천착한 문제는 단순히 '채팅이 나쁘다'가 아니라 **"AI 도구가 개발자의 몰입 상태를 어떻게 망가뜨리는가"** 였습니다. UX Tools 팟캐스트 "Designing The Next Flow State"에서 그는 이렇게 말했습니다.

AI를 사이드바에 박아 넣는 현재의 패턴 — 코드 쓰다가 채팅창으로 전환, 답 받으면 다시 코드로 복귀 — 은 사실 플로 스테이트를 반복적으로 파괴하는 구조입니다. 진짜 AI 네이티브 인터페이스는 개발자가 "타이핑과 읽기" 사이를 왔다갔다 하지 않도록 **의도(intention)를 먼저 선언하고, 실행은 에이전트가 맡는 구조**여야 한다는 것입니다.

이 철학은 Intent 제품 설계에 그대로 반영됐습니다.

### 3. Intent — IDE 이후의 세계를 실물로 만들다

2026년 Augment Code가 공개한 **Intent**는 Wattenberger의 설계 철학을 제품화한 결과물입니다. 핵심 개념은 "워크스페이스(workspace)"입니다.

Augment Code는 공식 발표에서 이렇게 설명했습니다:
> *"One agent is great. Two work. Past that, things fall apart fast. Prompts go stale, context lives everywhere, and you end up spending more time on overhead than actual work."*

Intent는 이 문제를 해결하기 위해 각 작업마다 독립된 워크스페이스를 생성합니다. 한 워크스페이스 안에는 **코드베이스 사본(별도 브랜치 + Git worktree), 에이전트 집합, 마크다운 노트, 터미널, 스펙 문서**가 하나의 묶음으로 들어있습니다. 여러 워크스페이스를 동시에 열어 놓고 전환해도 Git 브랜치를 머릿속에서 관리하거나 흩어진 채팅 기록을 뒤질 필요가 없습니다.

기본 에이전트 구성은 **조율자(coordinator) → 구현자(implementer) → 검증자(verifier)** 의 3계층 퍼스나로 출시됐고, 모든 역할은 자연어 설정으로 커스터마이징 가능합니다.

### 4. "센티언트 디자인" — AI를 인터페이스 재료로 다루기

Wattenberger가 2026 컨퍼런스에서 강연한 개념 **Sentient Design(센티언트 디자인)**은 그의 사상적 정점입니다. 정의는 간결합니다.

> *"Dashboards that design themselves, apps that manifest on demand, agents that just get it done."*  
> (한국어 의역) "스스로 설계되는 대시보드, 필요할 때 소환되는 앱, 그냥 해내는 에이전트."

핵심은 AI를 "도구의 도구"(채팅창)로 다루지 말고, **인터페이스 자체의 구성 재료**로 다루라는 것입니다. 버튼 하나가 클릭되는 순간 에이전트가 문맥을 파악하고 적절한 UI를 생성하는 방식 — 인터페이스가 사용자의 의도를 대기하다가 실행하는 구조입니다.

또한 그의 2026년 강연 제목 **"Your Design File Is Now an Agent Input"** 은 디자이너의 역할 전환을 직격합니다. 디자인 파일이 이제 사람이 보는 시각 참고물이 아니라 에이전트가 읽는 스펙 문서가 된다는 선언입니다.

### 5. GitHub Next의 유산 — 실험이 제품이 됐다

Wattenberger가 GitHub Next에서 수행한 연구들(코드베이스를 캔버스로 보는 인터페이스, 에이전트가 PR을 단계별로 가시화하는 UI 등)은 당시 "미래 실험"이었지만, 2년 후 Intent라는 상용 제품의 DNA가 됐습니다. 이 궤적 자체가 그의 방법론을 증명합니다: **프로토타입을 빠르게 만들고, 실제 개발자 워크플로에서 검증하고, 실패한 가정을 버려가며 제품화한다**.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro):**  
비서앱 채팅 입력창 옆에 "맥락 범위" 토글 1개를 설계합니다. 예를 들어 체크박스로 `[오늘 업무만]` vs `[전체 프로젝트]`를 선택하면, 에이전트에 전달되는 시스템 프롬프트의 날짜 범위나 참조 데이터 범위가 달라지는 구조입니다. 채팅창 하나를 그대로 두되, 슬라이더나 드롭다운 하나만 추가해도 어포던스가 달라집니다. 이것이 Wattenberger식 "boo chatbots" 철학의 가장 빠른 구현입니다.

**이번 주 1-2시간 (mid):**  
ERP나 비서앱에 "워크스페이스" 개념을 하나 이식합니다. 예를 들어 "와당탕 8월 행사 준비"라는 워크스페이스를 만들면, 그 안에 관련 체크리스트, 에이전트 대화 기록, 관련 메모가 하나의 컨텍스트로 묶입니다. 현재 분산돼 있는 옵시디언 노트 + 비서앱 채팅 + 체크리스트를 하나의 "작업 컨텍스트 묶음"으로 연결하는 설계입니다.

```python
# 비서앱 워크스페이스 컨텍스트 묶음 예시
workspace = {
    "id": "wadangtang_aug_event",
    "scope": "2026-08-01 ~ 2026-08-31",
    "spec": "8월 팝업 이벤트 운영 계획",
    "linked_notes": ["행사_체크리스트.md", "벤더_연락처.md"],
    "agent_persona": "운영 조율자 — 실행 가능한 다음 단계만 제시",
    "status": "in_progress"
}
```

**이번 달 실험 (macro):**  
비서앱에서 "채팅 우선" UX와 "워크스페이스 우선" UX를 병렬 운용해 봅니다. 채팅 우선은 지금처럼 프리폼 대화로 업무를 처리하고, 워크스페이스 우선은 모든 작업을 사전에 스펙 문서 + 에이전트 페르소나 + 컨텍스트 범위로 선언하고 시작합니다. 한 달 뒤 **"다시 물어본 횟수"(컨텍스트 재설명 비용)**와 **"완료 속도"** 두 지표를 비교합니다.

## 한국 솔로 운영자 맥락에서 주의

**첫째, "intent-first UI"는 작업 분류 체계가 선행돼야 합니다.** Intent가 워크스페이스를 묶음 단위로 관리하는 것은, Augment Code처럼 코드베이스 + Git worktree가 명확히 분리된 환경을 전제합니다. 와당탕·느린호밀처럼 행사 운영, 발주, SNS, 강의가 혼재하는 솔로 운영 환경에서는 "어떤 단위가 한 워크스페이스인가"를 먼저 정의하지 않으면 워크스페이스가 쓰레기통이 됩니다. 먼저 카테고리를 3-5개로 고정하세요.

**둘째, 설계의 완성도를 위해 고객을 기다리게 해선 안 됩니다.** Wattenberger의 철학은 내부 개발자 도구 설계에서 출발했습니다. 대표님의 비서앱은 자기 자신이 1호 사용자인 동시에 빌더입니다. "어포던스가 명확한 아름다운 UI"를 만드느라 실제 업무 처리를 미루는 함정이 있습니다. 채팅창 + 토글 하나로 시작하고, 나중에 UI를 다듬으세요.

## 더 깊이 보려면

- [Intent: A workspace for agent orchestration — Augment Code](https://www.augmentcode.com/blog/intent-a-workspace-for-agent-orchestration)
- [Why Chatbots Are Not the Future — Amelia Wattenberger](https://wattenberger.com/thoughts/boo-chatbots/)
- [What Comes After the IDE — Refactoring.fm with Amelia Wattenberger](https://refactoring.fm/p/what-comes-after-the-ide-with-amelia)
- [Your Design File Is Now an Agent Input — YouTube](https://www.youtube.com/watch?v=ffQqstT5HFk)
- [Amelia Wattenberger: Designing The Next Flow State — UX Tools Podcast](https://www.uxtools.co/episodes/amelia-wattenberger-designing-the-next-flow-state)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: 채팅창에 똑같은 맥락을 매번 새로 설명해야 하는 솔로 운영자의 고통 — AI를 쓰면 쓸수록 컨텍스트 재설명 비용이 쌓인다.
- **숫자**: "에이전트 1개는 훌륭하다. 2개도 된다. 그 이상은 빠르게 무너진다." — Augment Code, 2026. 멀티에이전트 실패의 임계점은 3번째 에이전트부터.
- **삽질**: GitHub Next에서 5년간 "더 좋은 코드 에디터"를 만들려다 실패한 Wattenberger의 결론: 문제는 에디터가 아니라 에디터 외부의 조율 레이어였다. 솔로 운영자도 마찬가지 — 비서앱보다 비서앱들 사이의 조율이 병목이다.
- **훅**: "여러분 회사의 AI 도구가 진짜 AI 네이티브인지 확인하는 방법 하나 — 아직도 채팅창만 있으면, 그건 2022년 수준입니다."
