---
date: 2026-07-22
category: 팟캐스트·뉴스레터
subject: Gergely Orosz (The Pragmatic Engineer) — "느려야 빨라진다" 에이전틱 엔지니어링의 새로운 병목
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱에 "오늘 내가 AI에게 넘긴 작업" 로그를 오늘 하루치만 작성 — 스펙을 내가 직접 쓴 것과 AI에게 맡긴 것 분리해 두 줄로 기록
---

# Gergely Orosz — "느려야 빨라진다": 에이전틱 엔지니어링 시대의 새로운 병목

## 누구/무엇인가

Gergely Orosz는 Uber, Skype/Microsoft를 거친 전직 시니어 엔지니어로, 2020년 풀타임 뉴스레터 작가로 전향한 뒤 *The Pragmatic Engineer*를 구독자 **110만 명, Substack 기술 카테고리 4위(소프트웨어 엔지니어링 1위)**로 키워냈습니다. 광고 없이 월 $15·연 $150 유료 구독만으로 운영하며, 매주 화요일 딥다이브·목요일 The Pulse·격주 팟캐스트 세 트랙을 1인 체제로 발행합니다. 전작 딥다이브(5/13)에서는 그의 뉴스레터 OS와 2026년 초 AI 툴링 설문(906명)을 다뤘습니다. 오늘은 그가 2026년 상반기 내내 파고든 핵심 테제, 즉 **"에이전트가 코드를 쓰는 시대에 병목은 오히려 인간의 명세(Specification)와 판단으로 이동했다"**는 주장을 집중 해부합니다.

## 무엇이 특별한가

### 1. "Slow Down to Speed Up" — 생산성 역설의 현장 진단

Orosz는 2026년 6월 부다페스트 Craft Conference 기조연설 〈Slow Down to Speed Up〉에서 소프트웨어 엔지니어링계의 불편한 진실을 정면으로 꺼냈습니다.

> *"AI agents are writing code pretty much everywhere, [but] most teams and companies are not seeing dramatic productivity gains."*
> "에이전트가 거의 모든 곳에서 코드를 쓰고 있지만, 대부분의 팀과 회사는 극적인 생산성 향상을 경험하지 못하고 있습니다."

그의 진단은 명확합니다. 병목이 **'코드 작성'에서 '명세·의사결정·검증'**으로 이동했는데, 팀들은 여전히 '더 빨리 코드 생성'에만 집중한다는 것입니다. AI 에이전트에게 모호한 지시를 던지고 빠른 출력을 기대하면 AI 슬롭(slop) — 겉으로는 그럴듯하지만 에러 핸들링과 보안이 구멍 난 코드 — 만 쌓입니다. 의도를 천천히, 구체적으로 정의하는 시간을 먼저 써야 에이전트 실행이 빨라진다는 역설입니다. 같은 맥락에서 그는 X에 이렇게 썼습니다:

> *"Talked with 2× 'AI-pilled' founders who are very productive devs, are building their startups. It remains damn hard, AI or not."*
> "AI에 완전히 꽂힌 생산성 높은 창업자 둘과 대화했는데, 여전히 지독히 어렵다. AI가 있든 없든."

AI가 PMF(제품-시장 적합성) 탐색 자체를 쉽게 만들지는 않는다는 솔직한 고백입니다.

### 2. 세 가지 엔지니어 아키타입 — Builders vs Shippers vs Coasters

AI 툴링 영향 리포트 〈The Impact of AI on Software Engineers in 2026〉에서 Orosz는 응답자들을 세 아키타입으로 분류했습니다.

- **Shippers(출하자)**: 빠르게 제품을 프로덕션으로 내보내는 데 집중. AI와 궁합이 가장 좋고 만족도도 가장 높습니다. 설문에서 "AI 덕분에 내 역할이 더 즐거워졌다"는 응답 비율이 단연 1위.
- **Builders(구축자)**: 더 크고 깊은 코드 변경을 다루는 그룹. AI 에이전트가 쏟아내는 코드를 리뷰해야 하는 부담이 폭증했습니다. "전문가 정체성 상실"과 동료의 AI 슬롭에 대한 좌절을 가장 많이 호소한 그룹.
- **Coasters(타성주행자)**: 주로 경험이 적은 개발자로, AI 덕분에 빠르게 출력물을 만들지만 역량 축적 경로가 불분명합니다. 이들이 만든 AI 슬롭이 Builders의 리뷰 부담을 키웁니다.

와당탕연구소 관점에서 가장 중요한 인사이트는 이것입니다. **솔로 빌더는 Shipper와 Builder를 동시에 겸해야 합니다.** Coaster 모드로 빠지는 순간, 빠른 출력은 나오지만 스펙 설계 역량이 비어 갑니다.

### 3. "Loop Engineering"과 "Context Engineering" — AI와 협업하는 두 가지 언어

Orosz는 2026년 중반 두 개의 새 프레임워크를 연속 커버했습니다.

**Loop Engineering**: 에이전트를 작동시키는 제어 시스템 설계. 구조는 단순합니다. (1) 트리거가 에이전트를 시작하고, (2) 검증자(verifier)가 목표 대비 결과를 확인하고, (3) 목표 달성 또는 한계 도달까지 재시도. Google 엔지니어 Addy Osmani의 에세이가 이 개념을 바이럴로 만들었고, Orosz는 독자 2,000명 이상이 공유한 이 논의를 심층 해설했습니다.

**Context Engineering**: HumanLayer의 Dex Horthy와의 인터뷰에서 Orosz는 실용적 결론을 도출했습니다. 대부분의 엔지니어에게 Loop Engineering 심층 스터디보다는 **AI 컨텍스트 윈도우를 이해하고 잘 설계하는 것**이 더 즉각적으로 유용하다는 것입니다. 무엇을 컨텍스트에 넣고 빼느냐가 에이전트 품질의 핵심입니다.

와당탕연구소의 Claude Code 비서앱·ERP 개발에 직결되는 관점입니다. CLAUDE.md 파일이 곧 Context Engineering의 실전 도구입니다.

### 4. "주의력이 새로운 병목" — OpenAI·Anthropic·Cursor 방문기

2026년 6월 30일 발행한 〈Impressions from Visiting OpenAI, Anthropic, & Cursor〉에서 Orosz는 샌프란시스코 사무실을 직접 방문한 뒤 공통 결론을 하나 뽑았습니다.

> 세 회사 모두 **클라우드 에이전트에 올인**하고 있으며, 수요가 대규모로 증가할 것으로 예상한다.

방문 중 OpenAI에서 확인한 수치가 인상적입니다. **내부 비엔지니어의 95% 이상이 ChatGPT가 아니라 Codex(에이전트 코딩 툴)를 사용**합니다. 그리고 엔지니어 @steipete의 글을 Orosz가 인용·증폭한 한 줄이 현 시대를 정확하게 압축합니다.

> *"Six months ago, my bottleneck was tokens. Then I joined OpenAI. Now my bottleneck is attention."*
> "6개월 전 내 병목은 토큰이었습니다. 그런데 OpenAI에 합류하고 나서, 이제 병목은 주의력입니다."

같은 맥락에서 그는 OpenCode(Dax Raad와의 에피소드)에서 이렇게 정리했습니다.

> *"Even with AI agents, the daily bottleneck is still deciding what you should do, not doing it."*
> "AI 에이전트가 있어도, 일상적 병목은 여전히 '무엇을 해야 할지 결정하는 것'이지 '하는 것'이 아닙니다."

### 5. "AI는 일을 더 쉽게 만들지 않는다" — 스킬 위축 경고

7월 AMA 에피소드에서 Orosz는 가장 불편한 AI 핫테이크를 직접 발언했습니다.

> *"AI doesn't make work easier, and be mindful of skill atrophy."*
> "AI는 일을 더 쉽게 만들지 않습니다. 스킬 위축에 주의하세요."

이어지는 설명이 더 날카롭습니다.

> *"If you're using AI and life seems to be getting a lot easier, it raises the question: are you trying hard enough?"*
> "AI를 쓰는데 삶이 훨씬 쉬워지고 있다면, 한 가지 질문이 생깁니다 — 당신은 충분히 어려운 문제에 도전하고 있나요?"

집중할 때 AI는 "마치 메크 슈트를 입은 것처럼" 강력하지만, 모호하게 쓰면 "그냥 그저 그렇다"고 그는 정리합니다. 스킬 위축 경고는 특히 솔로프리너에게 심각합니다. 팀이 없으면 동료가 미흡한 스킬을 보완해 주지 않습니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱에 "오늘 내가 AI에게 넘긴 작업" 로그를 오늘 하루치만 작성. 스펙을 내가 직접 쓴 것과 AI에게 맡긴 것 분리해 두 줄로 기록. 이 로그가 Context Engineering 역량 지도의 시작점입니다.

**이번 주 1-2시간 (mid)**: ERP·비서앱의 가장 잦은 에이전트 작업 하나를 골라 Loop Engineering 구조로 재설계. 트리거 → 실행 → 검증자 → 재시도/종료 네 단계를 CLAUDE.md 코멘트로 명시. 코드 스니펫 예시:

```markdown
<!-- LOOP: 주문 입력 에이전트 -->
<!-- TRIGGER: 카카오 주문 메시지 수신 -->
<!-- GOAL: orders 테이블에 row 삽입 + 재고 차감 -->
<!-- VERIFY: row 존재 확인 + 재고 수량 >= 0 -->
<!-- RETRY: 최대 2회, 실패 시 Slack 알림 -->
```

**이번 달 실험 (macro)**: "Slow Down to Speed Up" 파일럿. 다음 기능 개발 1건을 AI에게 먼저 넘기기 전에 명세 문서(1페이지)를 먼저 작성하는 프로세스 도입. 측정 지표: 명세 작성 시간 vs. 코드 리뷰·수정 시간 비교. 2주 후 비서앱 메모로 결과 기록.

## 한국 솔로 운영자 맥락에서 주의

**Gergely의 프레임이 '팀 있는 회사' 기준**입니다. AI 슬롭을 리뷰하는 Builder 역할과 출시하는 Shipper 역할이 솔로에게는 동일인입니다. 리뷰 부담이 쌓여도 알아줄 동료가 없으니, Coaster 모드로 빠지는 것을 혼자 감지해야 합니다. 옵시디언 로그가 이를 잡아내는 유일한 외부 거울입니다.

**"스킬 위축 경고"의 한국 맥락**: 강의·콘텐츠 사업자로서 실제 구현 역량이 곧 강의 신뢰성입니다. AI로 다 해결하는 것처럼 보이는 콘텐츠는 초반엔 인기를 끌지만, 스킬 위축이 누적되면 고급 질문에 대한 답변 깊이가 얕아집니다. AI는 보조 수단으로만 사용하고, 어려운 문제는 여전히 직접 씨름하는 습관이 필요합니다.

## 더 깊이 보려면

- [Slow Down to Speed Up (newsletter)](https://newsletter.pragmaticengineer.com/p/slow-down-to-speed-up)
- [Craft Conference 2026 기조연설 YouTube](https://www.youtube.com/watch?v=5wks1W-auKY)
- [AI Tooling 2026 설문 결과](https://newsletter.pragmaticengineer.com/p/ai-tooling-2026)
- [The Impact of AI on Software Engineers 2026](https://newsletter.pragmaticengineer.com/p/the-impact-of-ai-on-software-engineers-2026)
- [Impressions from visiting OpenAI, Anthropic & Cursor](https://newsletter.pragmaticengineer.com/p/impressions-from-visiting-openai)
- [What is "Loop Engineering"?](https://newsletter.pragmaticengineer.com/p/what-is-loop-engineering)
- [The Pragmatic Engineer AMA](https://newsletter.pragmaticengineer.com/p/the-pragmatic-engineer-ama)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: 에이전트가 코드를 쓰는데 왜 나는 더 바쁠까? — 병목이 코드 작성에서 스펙·검증으로 이동했는데 일하는 방식은 그대로이기 때문.
- **숫자**: 906명 설문에서 75%가 AI로 절반 이상의 작업을 처리하지만, OpenAI 방문에서 확인한 "주의력이 새 병목"은 이 숫자가 생산성 향상을 보장하지 않음을 말해 준다.
- **삽질**: AI 에이전트에게 모호한 명세를 던진 결과 겉보기엔 멀쩡한 코드가 나왔지만 에러 핸들링이 전혀 없어 두 시간 디버깅 — Builders가 가장 많이 호소하는 패턴.
- **훅**: "AI가 코드를 쓴다. 그런데 당신은 왜 더 바쁜가?" — Orosz의 Craft Conference 기조연설 첫 30초를 그대로 빌려 써도 좋다.
