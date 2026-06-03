---
date: 2026-06-04
category: 시스템방법론
subject: Amelia Wattenberger — 구현이 끝나고 의도가 시작된다
tags: [AI탐구, deepdive]
starred: false
micro_action: 옵시디언에서 비서앱/ERP 미해결 기능 하나를 골라 coordinator-implementer-verifier 3줄 spec 노트로 작성해보기
---

# Amelia Wattenberger — 구현이 끝나고 의도가 시작된다

## 누구/무엇인가

Amelia Wattenberger는 신경과학·심리학을 전공한 뒤 프로그래머로 커리어를 바꾼 뒤, 8년간 프론트엔드 개발자로 일하다 어느 순간 명함에 "디자이너"라는 단어가 추가된 독특한 배경을 지닌 인물입니다. 600페이지가 넘는 *Fullstack D3 and Data Visualization* 책을 집필했고, 2023년 AI.Engineer Summit에서 "Climbing the Ladder of Abstraction" 강연으로 AI 인터페이스 설계 커뮤니티에 이름을 알렸습니다. GitHub Next(미래 개발자 도구 프로토타입 팀)의 Staff Research Engineer로 활동하며 Code Brushes, Code Atlas, Copilot for Docs 등 실험적 인터페이스를 만들었고, 현재는 Sutter Hill Ventures 파트너이자 Augment Code의 Product Lead로서 에이전트 오케스트레이션 워크스페이스 **Intent**를 설계하고 있습니다. 2026년 3월 Refactoring.fm 팟캐스트에 출연해 "IDE 이후의 세계"를 주제로 한 인터뷰가 개발자 커뮤니티에서 큰 반향을 일으켰습니다.

## 무엇이 특별한가

### 1. 추상의 사다리(Ladder of Abstraction) — AI는 줌 렌즈다

2023년 강연에서 Wattenberger는 구글 맵을 비유로 들었습니다. 지도를 확대하면 골목 이름이 보이고, 축소하면 대륙 윤곽만 남습니다. 맥락에 따라 표시되는 정보의 층위가 달라지는 것입니다. 그녀는 "LLM도 마찬가지로 데이터를 이 줌 레벨에 맞게 재구성할 수 있어야 한다"고 주장했습니다. 현재 대부분의 AI 도구가 모든 정보를 같은 해상도로 쏟아내는 반면, 잘 설계된 AI 인터페이스는 사용자의 현재 추상화 수준에 맞는 정보만 선택적으로 노출해야 한다는 것이 핵심 주장입니다. 이 개념은 후에 Intent의 spec-driven 설계 철학으로 이어집니다.

### 2. 구현(Implementation) → 의도(Intention) 이동

Wattenberger는 최근 인터뷰에서 이렇게 말합니다: *"The work has changed shape, but the tools haven't caught up yet."* (일이 바뀌었는데, 도구는 아직 따라오지 못했다.) 신택스 하이라이팅, REPL, 핫 리로딩, 타입 체커 등 수십 년간 IDE는 개발자의 "생각하는 방식"에 맞춰 진화했습니다. 그런데 AI 에이전트가 코드 구현을 처리하기 시작하자, 개발자의 실제 작업은 더 높은 추상 층으로 이동했습니다. 코드 한 줄을 어떻게 쓸지가 아니라, 무엇을 만들지·왜 만들지·어떤 순서로 검증할지가 핵심 역할이 된 것입니다. 이것이 그녀가 "구현에서 의도로의 이동"이라고 부르는 현상입니다.

### 3. Intent — Spec이 새로운 소스 오브 트루스

Intent의 핵심 설계 단위는 **워크스페이스**입니다. 하나의 작업에 대해 독립된 환경을 하나 띄우고, 그 안에 코드베이스의 git worktree 사본, 에이전트 집합, 마크다운 노트, 터미널, 그리고 **spec**이 함께 번들됩니다. Spec은 단순한 초기 기획서가 아니라 작업이 진행되는 내내 업데이트되는 살아있는 문서입니다. 에이전트 오케스트레이션 방식도 의도적으로 설계됐습니다: Coordinator 에이전트가 spec을 파악해 계획을 잡고, Implementer 에이전트들이 병렬로 작업하며, Verifier 에이전트가 결과를 spec과 대조해 불일치·버그·누락을 잡아냅니다. 기본 페르소나로 탑재되어 있으나, 자연어 설정으로 전부 조정 가능합니다.

### 4. Notes 패턴 — 대화 스레드 바깥의 영속적 컨텍스트

Intent 팀이 개발하며 발견한 핵심 패턴이 **Notes**입니다. 멀티에이전트 시스템에서 가장 자주 발생하는 장애는 컨텍스트 소실 — 어떤 에이전트가 무엇을 했는지, 다른 에이전트가 알지 못하는 상황입니다. Notes는 대화 스레드 외부에 구조화된 형태로 저장되는 메모로, "코디네이터의 노트를 항상 최신 상태로 유지하면 에이전트 군단 전체가 같은 맥락을 공유한다"는 원칙을 구현합니다. 이것은 솔로 운영자가 Claude Code에서 CLAUDE.md나 context.md를 관리하는 것과 본질적으로 같은 패턴입니다.

### 5. 개발자의 플로우 스테이트를 애도하다

2026년 UX Tools 팟캐스트에서 Wattenberger는 "개발자들이 예전 플로우 스테이트를 애도하고 있다"고 표현했습니다. 깊이 집중해 코드에 몰입하던 그 상태, IDE 안에서 스물스물 문제를 해결해 나가던 리듬이 AI가 코드를 대신 쓰면서 사라졌다는 것입니다. 그녀의 주장은 "플로우 스테이트 자체를 포기하는 것이 아니라, 새로운 종류의 플로우 스테이트를 설계해야 한다"는 것입니다. 의도와 방향 설정, spec 작성, 에이전트 오케스트레이션에서 오는 새로운 몰입이 그 답입니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 옵시디언에서 비서앱 또는 ERP의 미해결 기능 하나를 골라 아래 3줄 spec 노트를 작성해보세요. `## Coordinator:` (목표 1문장) / `## Implementer:` (구현 단계 3개) / `## Verifier:` (완료 기준 2개). Claude Code에 이 노트를 첨부해서 작업 지시하면, 지시의 품질이 달라집니다.

**이번 주 1-2시간 (mid)**: 비서앱의 반복 수동 작업(예: 일정 정리·메모 분류) 하나를 골라 Wattenberger의 워크스페이스 구조를 흉내 내보세요. CLAUDE.md에 해당 기능의 spec 섹션을 만들고, coordinator(목표) → implementer(단계) → verifier(완료 체크리스트) 형태로 정리합니다. 이후 Claude Code로 구현 요청 시 이 spec을 항상 참조하게 합니다.

```markdown
<!-- CLAUDE.md 에 추가할 spec 섹션 예시 -->
## Feature Spec: 일일 업무 요약 자동 생성

### Coordinator
매일 오후 6시, 당일 완료된 업무와 미완료 항목을 슬랙 메시지 형태로 요약한다.

### Implementer
1. 당일 tasks 테이블에서 완료/미완료 항목 쿼리
2. GPT-4o mini로 3문장 요약 생성
3. 비서앱 API로 ledger에 기록 + 텔레그램 발송

### Verifier
- [ ] 요약에 날짜·완료 수·미완료 수 포함 여부
- [ ] 텔레그램 수신 확인 (HTTP 200)
```

**이번 달 실험 (macro)**: 비서앱 또는 ERP 개발 시 "구현 코딩 시간" 대 "spec 작성 시간" 비율을 측정해보세요. Wattenberger의 주장대로라면, spec 작성에 30분을 써서 에이전트가 3시간치 코드를 생성한다면 전체 생산성이 6배입니다. 2주간 로그를 남겨 실제 비율을 측정하고 옵시디언 노트에 기록합니다.

## 한국 솔로 운영자 맥락에서 주의

**Intent는 팀 개발자를 위해 설계됐습니다.** 와당탕연구소처럼 혼자 개발하는 상황에서 coordinator-implementer-verifier 3-agent 구조를 그대로 복제하면 오히려 오버헤드가 생깁니다. 핵심만 가져올 것: spec 노트 패턴 + verifier 체크리스트 패턴. 에이전트 수를 늘리기보다 spec의 품질을 높이는 것이 솔로 운영자에게 더 실용적입니다.

**"의도 작업"도 결국 시간이 필요합니다.** Wattenberger의 프레임은 "구현은 AI가 해주니 나는 의도만 정의하면 된다"는 낙관론을 줄 수 있습니다. 그러나 좋은 spec을 쓰는 것 자체가 고도의 집중 작업입니다. 비서앱·ERP의 요구사항을 정확하게 정의하는 능력은 코딩 능력만큼이나 훈련이 필요합니다.

## 더 깊이 보려면

- [What Comes After the IDE — Refactoring.fm Podcast (2026-03-20)](https://refactoring.fm/p/what-comes-after-the-ide-with-amelia)
- [Designing The Next Flow State — UX Tools Podcast](https://www.uxtools.co/episodes/amelia-wattenberger-designing-the-next-flow-state)
- [Climbing the Ladder of Abstraction — AI Engineer Summit 2023 (YouTube)](https://www.youtube.com/watch?v=PAy_GHUAICw)
- [Intent: A workspace for agent orchestration — Augment Code Blog](https://www.augmentcode.com/blog/intent-a-workspace-for-agent-orchestration)
- [Multi-Agent Orchestration Architecture Guide — Augment Code](https://www.augmentcode.com/guides/multi-agent-orchestration-architecture-guide)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "IDE는 수십 년간 개발자의 사고방식에 맞춰 진화했는데, AI가 등장한 후 일의 형태가 바뀌었는데 도구는 아직 따라오지 못했다." — Wattenberger 인터뷰. 지금 대표님이 Claude Code를 쓰면서 느끼는 '뭔가 안 맞는 느낌'의 정체가 바로 이겁니다.
- **숫자**: Fullstack D3 책 600+ 페이지 → 데이터 시각화 커뮤니티 표준 교재. GitHub Next에서 Code Brushes·Code Atlas·Copilot for Docs 3개 프로토타입을 단독으로 설계. 배경이 신경과학이라는 점 — AI 인터페이스를 인간 인지 구조 기반으로 설계하는 드문 인물.
- **삽질**: "AI를 기존 IDE에 그냥 얹었더니 채팅창이 생겼다." GitHub Copilot Chat이 처음 나왔을 때의 반응이 정확히 이것. Wattenberger 본인도 GitHub에서 이 문제를 해결하려 Code Brushes(포토샵 브러시처럼 코드를 페인팅)를 만들었지만, 근본 패러다임 교체 없이는 한계가 있었음을 인정합니다.
- **훅**: "당신이 AI에게 코드를 짜달라고 하는 방식, 그건 아직 낡은 패러다임입니다. 지금부터 'spec을 쓰는 사람'으로 전환하는 30분 실험을 해보겠습니다."
