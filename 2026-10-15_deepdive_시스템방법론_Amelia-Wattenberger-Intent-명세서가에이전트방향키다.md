---
date: 2026-10-15
category: 시스템방법론
subject: Amelia Wattenberger — Intent, 명세서가 에이전트의 방향키다
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱 또는 ERP에서 오늘 만들 기능 하나를 "목표 / 완료 기준 / 에이전트 지시사항" 3단 명세 포맷으로 먼저 작성한 뒤 Claude Code에 던져보기
---

# Amelia Wattenberger — Intent, 명세서가 에이전트의 방향키다

## 누구/무엇인가

Amelia Wattenberger는 데이터 시각화와 인터페이스 설계 분야에서 가장 영향력 있는 실천가 중 한 명입니다. *Fullstack D3 and Data Visualization* 책의 저자이자, GitHub Next 팀의 Principal Research Engineer로 AI 코딩 도구의 초기 세대를 설계했습니다. 2026년 현재 그는 Sutter Hill Ventures의 파트너이자 **Augment Code의 Product Lead**로, AI 에이전트 시대를 위한 새로운 개발 환경 **Intent**를 직접 설계하고 출시했습니다.

Intent는 2026년 2월에 공개된 "에이전트 오케스트레이션 워크스페이스"입니다. 단순히 AI 자동완성이나 채팅 기반 코딩 도우미가 아니라, 여러 에이전트가 병렬로 작업하는 흐름 전체를 인간이 설계하고 감독하는 환경입니다. Claude Code, Codex, OpenCode 등 서드파티 에이전트와도 연동됩니다. Wattenberger의 핵심 주장은 하나입니다: **에이전트 시대의 새로운 작업 단위는 '대화(conversation)'가 아니라 '명세서(spec)'다.**

## 무엇이 특별한가

### 1. 대화가 아닌 명세서를 작업 단위로 삼는다

기존의 채팅 기반 AI 도구들은 "대화 스레드"를 작업의 단위로 사용합니다. 하지만 Wattenberger는 이 모델이 에이전트가 복잡한 작업을 수행할 때 근본적으로 부서진다고 주장합니다. Intent에서 각 작업은 독립된 **Git worktree**에 격리됩니다. Worktree 안에는 코드, 계획, 터미널, 리뷰 도구, 그리고 에이전트들이 함께 들어있습니다. "대화가 끝나도 작업은 계속된다"는 원칙이 설계 전체를 관통합니다.

### 2. "살아있는 명세서" — 에이전트가 업데이트한다

Intent의 코디네이터 에이전트는 Augment의 Context Engine으로 코드베이스를 이해한 뒤, 작업을 명세서(spec)로 변환합니다. 인간이 이 명세서를 **승인하기 전까지는 코드를 한 줄도 쓰지 않습니다.** 그런데 여기서 차별점이 있습니다. 명세서는 작업이 진행되면서 에이전트들이 계속 업데이트하는 "살아있는 문서"입니다. Wattenberger가 별도 에세이(What Spec-Driven Development Gets Wrong)에서 밝힌 것처럼, "낡은 명세서는 맥락을 모르는 에이전트를 잘못된 방향으로 이끈다." 명세서의 신선도가 곧 에이전트의 정확도입니다.

### 3. 6개 특화 에이전트 + 인간 승인 게이트

Intent의 내부에는 역할이 분리된 6개 에이전트가 있습니다: **Investigate(조사), Implement(구현), Verify(검증), Critique(비판), Debug(디버그), Code Review(코드 리뷰)**. 코디네이터가 계획을 세우면 구현 에이전트들이 **웨이브(wave)** 방식으로 병렬 작업을 수행하고, 버리파이어가 명세서 대비 결과를 검증합니다. 인간은 각 단계의 주요 게이트에서만 개입합니다. "모든 것을 통제하는 것"이 아니라 "결정이 필요한 순간에만 개입하는 것"이 설계 원칙입니다.

### 4. IDE 이후 시대의 새 인터페이스 — "마지막 30%가 가장 어렵다"

Wattenberger는 Changelog 팟캐스트 인터뷰("Exploring with agents")에서 에이전트 도구의 진화를 세 시대로 나눴습니다: Copilot의 자동완성 시대 → ChatGPT의 채팅 시대 → CLI/에이전트 시대 → 그리고 지금은 다시 UI가 돌아오는 **앱 시대**. 아이러니하게도 에이전트가 코드를 대부분 쓰게 되면, "마지막 30%"가 가장 어려운 병목이 됩니다. 에이전트가 처음 80%는 빠르게 처리하지만, 비즈니스 도메인 지식과 엣지 케이스가 뒤섞인 마지막 구간은 인간의 판단이 필수입니다. Intent는 그 마지막 30%를 위한 인터페이스입니다.

### 5. "놀이가 생산성보다 중요하다"

Kent Beck과의 대담에서 Wattenberger는 에이전트 시대에 가장 희귀한 역량으로 **"언제 물러설지 아는 것(knowing when to step back)"**을 꼽았습니다. 그는 지금이 극도로 빠른 도구 발전 속에서 최적화보다 실험이 중요한 시기라고 말합니다: *"Play matters more right now than productivity."* (지금 이 순간, 놀이가 생산성보다 중요하다.) 이 발언은 솔로 운영자에게 특히 의미심장합니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱 또는 ERP에서 오늘 만들 기능 하나를 다음 3단 포맷으로 먼저 작성한 뒤 Claude Code에 던져보기.
```
## 목표
[한 문장으로 무엇을 만드는가]

## 완료 기준
- [ ] 기준 1
- [ ] 기준 2

## 에이전트 지시사항
[맥락, 주의 사항, 제약 조건]
```
이 포맷이 Intent의 "살아있는 명세서"의 미니 버전입니다. Claude Code가 잘못된 방향으로 달리기 전에 인간이 방향을 잡는 습관을 만듭니다.

**이번 주 1-2시간 (mid)**: CLAUDE.md에 "명세서 섹션"을 추가해 현재 개발 중인 비서앱/ERP의 주요 기능 목록과 각 기능의 완료 기준을 작성합니다. 에이전트가 컨텍스트를 읽어 올 때 명세서도 함께 로드되도록 구성합니다. 예시:
```markdown
## 현재 진행 기능 명세
### ledger 색상 태그 필터 (진행중)
- 목표: 메모 목록에서 color별 필터링 가능
- 완료 기준: pink/green/yellow 색상 버튼 클릭 시 해당 색상 메모만 표시
- 에이전트 주의: 기존 검색 기능과 AND 조합 가능해야 함
```

**이번 달 실험 (macro)**: Intent 모델을 내 워크플로우에 이식합니다. 매 기능 개발 시작 전 "명세서 → Claude Code 던지기 → 리뷰 게이트 → 머지"의 4단 흐름을 30일간 실행하고, (1) 재작업 횟수, (2) 예상 대비 실제 소요 시간, (3) 에이전트가 명세서 없이 vs 있을 때 첫 결과 품질을 측정합니다. 명세서 작성 시간 15분이 재작업 2시간을 아끼는지 검증합니다.

## 한국 솔로 운영자 맥락에서 주의

**Intent는 팀 개발 흐름을 전제합니다.** 6개 특화 에이전트, 병렬 worktree, PR 기반 워크플로우는 엔터프라이즈급 코드베이스에 최적화된 구조입니다. 대표님처럼 비서앱+ERP를 혼자 운영할 때는 오케스트레이션 복잡성이 오히려 오버헤드가 될 수 있습니다. 핵심만 추출하세요 — "명세서 우선" 습관과 "인간 승인 게이트" 원칙은 팀 없이도 적용됩니다.

**"마지막 30%"는 사실 와당탕에는 더 큰 비중입니다.** 와당탕의 ERP는 비즈니스 로직(공구 날짜, 배송 계산, 인플루언서별 정산)이 극도로 도메인 특화되어 있습니다. 에이전트가 처음 70%를 빠르게 써줘도 도메인 지식이 녹아드는 마지막 30%에서 대표님이 직접 검토해야 합니다. 이 판단 비용을 최소화하는 것이 명세서 작성의 핵심 목적입니다.

## 더 깊이 보려면

- [Intent: A workspace for agent orchestration (Augment Code 공식 블로그)](https://www.augmentcode.com/blog/intent-a-workspace-for-agent-orchestration)
- [What spec-driven development gets wrong (Wattenberger, 2026)](https://www.augmentcode.com/blog/what-spec-driven-development-gets-wrong)
- [What Comes After the IDE — Refactoring Podcast](https://refactoring.fm/p/what-comes-after-the-ide-with-amelia)
- [Exploring with agents — The Changelog Interview](https://www.devshows.dev/podcasts/the-changelog/exploring-with-agents-(interview))
- [AI Engineer 2026 Speaker Profile](https://ai.engineer/speakers/amelia-wattenberger)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "에이전트한테 시켰더니 80%는 뚝딱 만들었는데, 내 비즈니스에 맞게 마지막 20%를 고치는 데 오히려 더 오래 걸렸다" — 이 고통이 Intent가 해결하려는 바로 그 문제입니다.
- **숫자**: Intent 출시 후 Augment Code의 에이전트 오케스트레이션 워크스페이스 접근 방식이 Cursor, Codex와 다른 제3의 카테고리로 언론에서 인용됨. GitHub Next 팀에서 수백만 개발자의 AI 코딩 패턴을 분석한 경험이 설계에 녹아있음.
- **삽질**: Wattenberger가 스펙 에세이에서 밝힌 것처럼, 초기 Intent 설계에서 명세서를 정적 문서로 다뤘을 때 에이전트들이 완성에 가까워질수록 명세서와 실제 구현이 벌어지는 문제가 발생했음. "살아있는 명세서"는 이 삽질에서 나온 해결책입니다.
- **훅**: "에이전트에게 '이거 만들어줘'라고 말하는 것과 '이게 완성됐을 때 어떤 상태인지'를 먼저 쓰는 것 — 이 두 접근의 결과 품질 차이가 10배입니다."
