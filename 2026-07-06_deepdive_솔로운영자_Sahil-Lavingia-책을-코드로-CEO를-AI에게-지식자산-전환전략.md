---
date: 2026-07-06
category: 솔로운영자
subject: Sahil Lavingia — 책을 코드로, CEO를 위임으로: 지식 자산의 AI 네이티브 전환
tags: [AI탐구, deepdive]
starred: false
micro_action: github.com/slavingia/skills 를 클론해서 /validate-idea 스킬 하나를 비서앱 현재 기능 아이디어 하나에 직접 실행해보기
---

# Sahil Lavingia — 책을 코드로, CEO를 위임으로: 지식 자산의 AI 네이티브 전환

## 누구/무엇인가

Sahil Lavingia(@shl)는 Gumroad(현 Anti-Work)의 창업자입니다. 인도네시아계 미국인으로 18세에 Pinterest의 두 번째 직원으로 일했고, 2011년에 Gumroad를 창업했습니다. 2021년에는 자신의 철학을 집대성한 책 *The Minimalist Entrepreneur*를 출간했으며, 지금도 많은 솔로 창업자들의 필독서로 꼽힙니다. Gumroad는 연매출 $10M(약 140억 원)의 크리에이터 수익화 플랫폼으로, 2026년 초 기준 크리에이터들에게 누적 $1B(약 1,400억 원)을 지급했습니다.

5월의 Deep Dive에서 그의 '코드베이스 토큰 수로 AI 속도를 측정하는' 전략을 다뤘다면, 오늘은 그 이후 일어난 두 가지 큰 변화에 집중합니다. 첫 번째는 2026년 3월, 그의 베스트셀러 책을 10개의 Claude Code 스킬로 변환한 것입니다. 두 번째는 2026년 초 Gumroad CEO 자리를 내려놓고 Ershad Kunnakkadan에게 넘긴 것입니다. 그는 이제 Chairman으로만 남아 있습니다.

## 무엇이 특별한가

### 1. 책이 실행 코드가 됐다 — 지식 자산의 새로운 형태

2026년 3월, Sahil은 GitHub에 `slavingia/skills` 레포지토리를 공개했습니다. *The Minimalist Entrepreneur*의 전체 방법론을 10개의 Claude Code 스킬(슬래시 커맨드)로 변환한 것입니다.

스킬 목록은 이렇습니다:
- `/find-community` — 타겟 커뮤니티 발굴
- `/validate-idea` — 시장성 검증
- `/mvp` — MVP 범위 정의
- `/processize` — 코드 전에 수동 프로세스 먼저
- `/first-customers` — 첫 100명 확보 전략
- `/pricing` — 지속 가능한 가격 설계
- `/marketing-plan` — 콘텐츠 마케팅으로 오디언스 구축
- `/grow-sustainably` — 수익성 유지하며 성장
- `/company-values` — 채용 전 문화 정립
- `/minimalist-review` — 모든 사업 결정의 미니멀리스트 체크

이 레포지토리는 공개 첫 주에 459K 뷰를 기록했고 4.8K 스타를 받았습니다. 각 스킬은 Markdown 파일 하나로 구성되어 있으며, 설치하면 Claude Code 세션 안에서 바로 호출됩니다. 책을 읽는 대신 AI와 대화하면서 프레임워크가 내 상황에 맞게 질문을 던지는 방식입니다.

> "Your AI applies the framework to your exact situation." — 스킬 소개 문구

이것이 왜 중요하냐면, 책의 유통 방식이 바뀌었기 때문입니다. 기존 책은 독자가 읽고 스스로 적용해야 했습니다. 스킬은 AI가 책의 논리를 내 프로젝트에 직접 실행합니다. Sahil은 자신의 지식 자산을 '읽히는 것'에서 '실행되는 것'으로 전환했습니다.

### 2. GOD Mode — 창업자 모드를 넘어선 위임의 철학

2024년 10월 Paul Graham의 '창업자 모드' 에세이가 화제가 됐을 때, Sahil은 즉시 *GOD Mode*라는 에세이로 응수했습니다. 그의 주장은 이렇습니다: 창업자 모드(Founder Mode)는 맞지만, 최고의 창업자는 공동창업자조차 동등하게 대하지 않는다는 것입니다.

그리고 그는 2026년에 이것을 실제로 실행했습니다. Gumroad(Anti-Work)의 CEO 자리를 Ershad Kunnakkadan에게 완전히 위임하고, 자신은 Chairman으로만 남았습니다. 회사의 일상 운영은 사람에게, 자신은 비전·철학·IP에 집중하는 구조입니다. 2026년 2월 바하마에서 열린 공개 연간 주주총회는 이 구조 전환을 공식화하는 자리였습니다.

이것이 그의 AI 철학과 맞닿습니다. 코드는 Devin이, 운영은 CEO가, 창업자는 '무엇을 왜 만드는가'만 설계합니다.

### 3. 40배 생산성 — 구체적인 AI 워크플로우

그가 공개한 개발 프로세스는 다음과 같습니다:

1. Deep Research로 무엇을 만들지 조사하며 대화
2. AI가 대화 내용을 기록해 spec으로 정리
3. spec에 디자인 요구사항 추가
4. Devin이 코드 작성
5. QA → 머지 → 자동 배포

도구는 v0(UI 프로토타이핑), Cursor(코드 편집), Devin(자율 코딩 에이전트)입니다. Gumroad 코드베이스는 2M 토큰, Flexile는 800K 토큰, Iffy는 200K 토큰, Shortest는 100K 토큰 — 각 제품의 AI 처리 가능성을 토큰 수로 관리합니다.

Flexile(계약자 관리 툴)의 경우 CSS 파일이 0개입니다. 181줄짜리 테마 파일 하나가 전체 디자인 시스템을 정의합니다. 이것이 AI가 스타일을 수정할 때 5,000줄 CSS를 뒤질 필요 없이 빠르게 처리하는 비결입니다.

> "Codebase architecture determines your AI velocity." — Sahil Lavingia

### 4. DOGE 55일과 실패에서 배운 교훈

2025년 3월-5월, Sahil은 DOGE(정부 효율화 부서)에서 자원봉사 소프트웨어 엔지니어로 55일을 보냈습니다. VA(재향군인부) 계약을 분석하는 LLM 기반 도구를 만들어 $1.6B 규모의 낭비를 식별했습니다. 하지만 언론에 노출된 직후 접근 권한이 박탈됐습니다.

그는 이 경험에서 두 가지를 인정했습니다: 도구에 결함이 있었고, 시간과 적절한 도구가 부족했다고. 이 자기비판은 그의 솔직한 커뮤니케이션 스타일과 일치합니다. Gumroad를 10억 달러 회사로 키우는 데 실패했다는 에세이(*Reflecting on My Failure to Build a Billion-Dollar Company*)를 쓴 사람답습니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: `github.com/slavingia/skills`를 클론해서 `/validate-idea` 스킬을 Claude Code에 설치한 뒤, 현재 비서앱에 추가하려는 기능 아이디어 하나에 직접 실행해보기. 스킬이 던지는 질문들이 기획 방향을 잡아줍니다. `micro_action`과 동일합니다.

**이번 주 1-2시간 (mid)**: Sahil의 `/processize` 스킬을 느린호밀의 주문 처리 플로우에 적용해보기. "코드 작성 전에 수동 프로세스를 먼저 설계하라"는 원칙은 ERP 기능 추가 때 특히 유효합니다. 아래 스니펫처럼 CLAUDE.md에 섹션을 추가해도 됩니다.

```markdown
## 기능 추가 원칙 (Processize 적용)
1. 코드 작성 전, 수동으로 3번 해본다
2. 반복되면 스크립트로, 그다음 UI로
3. 각 단계에서 '이게 정말 필요한가?' 점검
```

**이번 달 실험 (macro)**: 와당탕 운영 매뉴얼의 핵심 섹션 하나를 Claude Code 스킬로 변환해보기. 예를 들어 '고객 상담 응대 원칙'을 `/wadangtang-consult` 스킬로 만들면, 비서앱 세션마다 호출 가능한 실행 가능한 지식이 됩니다. 측정 지표: 스킬 호출 횟수, 응대 시간 단축율.

## 한국 솔로 운영자 맥락에서 주의

**"책 → 스킬" 전환은 원저작물의 깊이가 전제**입니다. Sahil의 스킬이 효과적인 이유는 *The Minimalist Entrepreneur*가 10년 이상의 창업 경험을 구조화한 콘텐츠이기 때문입니다. 깊이 없는 콘텐츠를 스킬로 만들면 AI가 빈 프롬프트를 실행하는 것과 같습니다. 먼저 콘텐츠의 깊이를 쌓은 뒤 코드화하는 순서가 중요합니다.

**CEO 위임 구조는 신뢰할 수 있는 운영자가 있을 때 가능**합니다. Sahil이 CEO를 내려놓을 수 있었던 건 Ershad라는 적합한 사람이 있었기 때문입니다. 솔로 운영자가 "AI가 운영하면 되지"라는 생각으로 위임 구조를 설계하면, 아직 AI는 실시간 고객 대응과 예외 상황 판단에서 인간 판단이 필요한 영역이 많습니다.

## 더 깊이 보려면

- [slavingia/skills GitHub 레포](https://github.com/slavingia/skills)
- [Gumroad 2026 연간 주주총회 YouTube](https://www.youtube.com/watch?v=ffkECKX-WgU)
- [GOD Mode 에세이](https://sahillavingia.com/god)
- [How Sahil Lavingia Runs $10M Gumroad with 1 Employee (Aakash G 뉴스레터)](https://www.news.aakashg.com/p/sahil-lavingia-podcast)
- [Gumroad × Devin 케이스스터디](https://devin.ai/customers/gumroad)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "책을 읽고 '나도 해야겠다'는 생각은 했는데, 내 상황에 어떻게 적용할지 모르겠다" — 한국 솔로 창업자 99%의 고충.
- **숫자**: 레포 공개 첫 주 459K 뷰 / 4.8K GitHub 스타 / Gumroad 크리에이터 누적 수익 $1B / 1명 직원으로 연매출 $10M.
- **삽질**: DOGE 55일 — LLM 도구를 급하게 만들었다가 언론 노출로 퇴출. "도구에 결함이 있었다"고 본인이 인정. AI 도구를 과신하고 검증 없이 배포한 결과.
- **훅**: "그는 자기 책을 Claude에게 넘겼습니다. 이제 Claude가 여러분에게 그 책을 가르칩니다."
