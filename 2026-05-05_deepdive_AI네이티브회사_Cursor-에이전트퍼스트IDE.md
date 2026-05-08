---
date: 2026-05-05
category: AI네이티브회사
subject: Cursor — 에이전트 퍼스트 IDE
tags: [AI탐구, deepdive]
starred: false
micro_action: "Cursor 무료 플랜으로 비서앱 코드베이스 열고 Agent Mode 켠 뒤 TODO 1개를 'Plan(Ask) → Implement(Agent)' 2단계 플로우로 처리해보기 (30분)"
---

# Cursor — "코드 편집기"에서 "에이전트 오케스트레이터"로

## 누구/무엇인가

Cursor는 2023년 MIT 출신 4명이 만든 AI 코딩 도구입니다. 처음엔 단순히 VS Code에 AI를 얹은 포크였지만, 2025년부터는 철학 자체가 달라졌습니다. 핵심 키워드는 **"개발자는 코드를 직접 쓰는 사람이 아니라, 에이전트를 지휘하는 오케스트레이터"**입니다.

CEO Michael Truell(당시 23세, 현재 25세)은 2025년 내내 "AI가 코드의 40~50%를 작성한다"는 데이터를 공유했고, 2026년 4월에는 Cursor 3를 출시하며 인터페이스 전체를 파일 편집 중심에서 에이전트 병렬 실행 중심으로 전면 재설계했습니다. 현재 2M+ 사용자, 50,000개 이상 엔지니어링 팀이 사용 중이고, Fortune 500의 약 70%가 고객사 안에 있습니다.

## 무엇이 특별한가

### 1. SaaS 역사상 최단 시간 $2B ARR 돌파

- 2025년 5월: $500M ARR
- 2025년 10월: $1B ARR (5개월 만에 2배)
- 2026년 2월: $2B ARR (4개월 만에 또 2배)
- 2026년 말 예상: $6B ARR 돌파

이 성장은 40~60명 팀이 만든 것입니다. Truell은 a16z 팟캐스트에서 "MIT 4명이 AI 에이전트 대신 코드 에디터를 만든 이유는, 에디터가 개발자와 AI의 접점이기 때문"이라고 설명했습니다. 단순한 제품이 아니라 **레버리지 극대화**가 핵심이었습니다.

### 2. 소프트웨어 개발 "3시대" 프레임

Truell과 공동창업자 Sualeh Asif는 개발 패러다임을 3단계로 정리했습니다:

- **1세대**: 파일을 직접 편집 (전통 IDE)
- **2세대**: 에이전트가 코드 대부분을 작성, 사람이 방향 지시 (현재 Cursor)
- **3세대**: 에이전트 무리가 자율적으로 기능을 배포

Cursor 3(2026년 4월 2일 출시)는 2세대에서 3세대로의 전환점입니다. 인터페이스를 처음부터 다시 설계해 "개발자가 코드보다 에이전트 관리에 더 많은 시간을 쓴다"는 전제를 UI에 반영했습니다.

### 3. Cursor 3: 병렬 에이전트 오케스트레이션 현실화

Cursor 3가 도입한 핵심 기능:

- **Agents Window**: 로컬·git worktree·클라우드·원격 SSH 환경에서 여러 에이전트를 동시에 실행. 각 에이전트의 상태·추론 과정·진행률을 사이드바에서 실시간 확인.
- **Background Agents**: 클라우드에서 수십 분간 자율 실행 후 PR 제안. 로컬↔클라우드 세션 핸드오프 지원.
- **Agent Tabs**: 여러 채팅을 나란히 또는 그리드로 배치.
- **Design Mode** (Cmd+Shift+D): 내장 브라우저에서 UI 요소를 직접 어노테이션.
- **플러그인 마켓**: Atlassian·Datadog·GitLab·Hugging Face 등 30+ 플러그인.

### 4. "바이브 코딩은 사상누각" — CEO의 직접 경고

Truell은 2025년 12월 Fortune Brainstorm AI에서 정반대의 경고를 직접 날렸습니다:

> *"If you close your eyes and you don't look at the code and you have AIs build things with shaky foundations as you add another floor, and another floor, and another floor, things start to kind of crumble."*
> ("눈을 감고 코드를 보지 않은 채 AI에게만 맡기면, 층을 올릴수록 기초가 흔들려 결국 무너집니다.")

자기 제품의 최대 오남용 패턴을 본인이 직접 공개 경고했다는 점이 인상적입니다. 코드를 이해하며 에이전트를 지휘하는 것과, 단순히 "바이브"로 결과물만 뽑는 것은 전혀 다른 레벨의 아웃풋을 만든다는 선언입니다.

### 5. 권장 워크플로우: Plan → Agent → Manual의 3단계

Cursor 사용자 커뮤니티에서 검증된 솔로 개발자 워크플로우:

1. **Ask 모드로 계획**: 무엇을 만들지 구조 설계
2. **Agent 모드로 구현**: 고수준 명령만 던지고 에이전트에게 다파일 수정 위임
3. **수동 편집으로 마무리**: 섬세한 조정이 필요한 부분만 직접

이 패턴이 "그냥 에이전트에게 말만 거는" 방식보다 현저히 나은 아웃풋을 낸다고 알려져 있습니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: Cursor 무료 플랜으로 비서앱 코드베이스 열고 Agent Mode 켠 뒤 TODO 1개를 'Plan(Ask) → Implement(Agent)' 2단계 플로우로 처리해보기. 지금 사용 중인 Claude Code와 워크플로우 차이를 직접 비교하는 게 목적.

**이번 주 1-2시간 (mid)**: Claude Code와 Cursor 3의 Background Agent를 동일한 ERP 태스크(예: "상품 테이블에 재고 알림 로직 추가")에 각각 투입해 결과물 품질·소요 시간·문맥 이해도를 비교 측정.

```bash
# Claude Code 방식 (현재)
claude "ERP 상품 테이블에 재고 임계값 컬럼 추가 + 알림 로직 구현"

# Cursor Background Agent 방식 (실험)
# 1. Cursor → Background Agents → New Agent
# 2. 동일 프롬프트 + 동일 컨텍스트 입력
# 3. 결과 PR 품질 비교 메모
```

**이번 달 실험 (macro)**: Cursor의 "Plan → Agent → Manual" 3단계 워크플로우를 느린호밀 주문/메뉴 관리 ERP 모듈 개발에 한 달간 적용. 측정 지표: 기능 1개당 소요 시간, 버그 수, 코드 리뷰 수정 횟수. 성공 기준: 현재 대비 30% 이상 개발 시간 단축.

## 한국 솔로 운영자 맥락에서 주의

**$20/월 ROI 계산을 먼저 해보세요.** Cursor Pro는 월 $20입니다. 이미 Claude Code를 쓰고 있다면 기능 중복이 상당합니다. 두 도구를 같이 쓰는 건 불필요한 비용이 될 수 있으므로, 위 mid 실험으로 명확히 비교한 뒤 선택하는 게 합리적입니다.

**"바이브 코딩 경고"는 와당탕 규모에서 더 치명적입니다.** 혼자 운영하는 비서앱+ERP는 리뷰해줄 동료가 없습니다. Truell의 경고처럼, 기초를 이해하지 못한 채 에이전트가 쌓아올린 코드는 나중에 대표님 혼자 디버깅해야 합니다. 에이전트가 생성한 코드라도 반드시 읽고 이해한 뒤 머지하는 습관이 솔로 운영자에게는 필수입니다.

## 더 깊이 보려면

- [Cursor 3 공식 블로그](https://cursor.com/blog/cursor-3)
- [Cursor 3 agent-first interface — InfoQ 분석 (2026.04)](https://www.infoq.com/news/2026/04/cursor-3-agent-first-interface/)
- [Cursor CEO vibe coding 경고 — Fortune (2025.12)](https://fortune.com/2025/12/25/cursor-ceo-michael-truell-vibe-coding-warning-generative-ai-assistant/)
- [Cursor $2B ARR 돌파 — TechCrunch (2026.03)](https://techcrunch.com/2026/03/02/cursor-has-reportedly-surpassed-2b-in-annualized-revenue/)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: 혼자 개발하면 코드 리뷰해줄 사람이 없다. 에이전트가 짠 코드를 에이전트가 검토한다 — 이게 진짜 솔로 개발의 위험.
- **숫자**: 40~60명 팀이 $2B ARR. 직원 1인당 연 $33M~50M 매출. 한국 대기업 평균의 100배.
- **삽질**: Cursor CEO 본인이 자기 제품의 오남용 패턴(바이브 코딩)을 공개 경고. "도구를 팔면서 도구의 함정도 함께 알려주는" 희귀한 사례.
- **훅**: "AI가 코드의 절반을 쓰는 시대에, 개발자의 새 직함은 '코더'가 아니라 '에이전트 오케스트레이터'입니다."
