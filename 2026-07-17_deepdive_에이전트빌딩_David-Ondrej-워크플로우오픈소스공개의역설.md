---
date: 2026-07-17
category: 에이전트빌딩
subject: David Ondrej — 워크플로우를 오픈소스로 풀수록 돈이 더 벌리는 역설
tags: [AI탐구, deepdive]
starred: false
micro_action: npx skills add davidondrej/skills 설치 후 skills/agent-orchestration/agent-self-scheduling 내용 읽고 비서앱 스케줄 에이전트 프롬프트에 핵심 패턴 1줄 이식해보기
---

# David Ondrej — 워크플로우를 오픈소스로 풀수록 돈이 더 벌리는 역설

## 누구/무엇인가

David Ondrej는 체코 출신의 AI 창업가이자 YouTuber입니다. 2023년 4월에 채널을 시작해 3년 만에 구독자 약 39만 명, 총 누적 조회수 2,400만 뷰를 달성했습니다. 단순히 강의를 파는 교육자가 아니라, 실제로 회사를 만들고 팔아본 창업가입니다. 그의 AI 생산성 앱 Vectal.ai는 $155,000 ARR을 달성한 뒤 Agent Zero에 180만 달러(약 24억 원)에 매각됐습니다. 이 엑싯이 그의 콘텐츠에 무게를 실어줍니다. 비슷한 이야기를 하는 AI 유튜버는 수천 명이지만, 실제로 회사를 팔아본 사람은 훨씬 적습니다. 현재는 New Society(Skool 커뮤니티), Scale Software AI(스타트업 엑셀러레이터), 그리고 7월에 공개한 오픈소스 스킬 패키지 `davidondrej/skills`를 동시에 운영하고 있습니다.

---

## 무엇이 특별한가

### 1. "SaaS는 죽었다" — 그러나 정확히 뭐가 죽은 건지가 핵심

2026년 상반기, David Ondrej는 X에 이렇게 썼습니다:

> *"SaaS is dead. Agents killed it."*

그러자 커뮤니티가 들끓었습니다. 그는 곧바로 정정했습니다:

> *"SaaS isn't dead. The easy SaaS moat is dead. Massive difference."*

이 두 문장의 간격에 그의 핵심 통찰이 있습니다. 에이전트가 등장하기 전까지, 솔로 창업가의 SaaS 해자는 '편리한 UI 래퍼'였습니다. API를 그럴듯하게 감싸고 온보딩 흐름을 깔끔하게 만들면 팔렸습니다. 지금은 에이전트가 그 레이어를 직접 대체합니다. 그러나 에이전트가 "대신 실행"해줄 수 없는 것 — 검증된 워크플로우, 커뮤니티 맥락, 도메인 신뢰 — 은 오히려 더 귀해졌습니다. 와당탕 대표님에게 직접 연결되는 포인트입니다. ERP나 비서앱이 AI API를 단순히 감싸는 "편리한 래퍼"라면 위험하지만, 와당탕만의 운영 흐름과 맥락이 녹아있다면 에이전트가 오히려 해자를 강화합니다.

### 2. 바이브 코딩으로 $10K MRR — "AI가 코드의 99.9%를 썼다"

David Ondrej는 X에 이렇게 밝혔습니다:

> *"i built a $10,000 MRR startup just by vibe coding. the AI wrote 99.9% of the code. yet some people will still call vibe-coding a scam. incredible…"*

그는 직접 코드를 한 줄도 쓰지 않고 SaaS를 만들어 월 1,300만 원 수준의 수익을 달성했습니다. 물론 '99.9% AI'라는 표현은 마케팅 언어입니다. 그러나 실제 메시지는 명확합니다. 이제 창업가의 핵심 역량은 코드 작성이 아니라 에이전트에게 올바른 지시를 내리는 것, 즉 컨텍스트 엔지니어링과 판단력입니다. Vectal.ai를 $155K ARR까지 키운 것도 같은 방식입니다.

### 3. 미니멀리즘 에이전트 — Claude Code에서 Pi로 공개 피벗

2026년 6월, David는 X에 예상 밖의 공개 전환을 발표했습니다:

> *"Pi has been my go-to agent over the past few days. I've been using all other AI Agents less and less. if you put in a few hours to learn it, Pi really is the shit."*

Pi 에이전트는 내장 도구 4개(read, write, edit, bash), 시스템 프롬프트 1,000토큰 이하, MCP 없음이 특징입니다. GitHub 스타는 46,000+. 그가 이 전환을 공개한 이유는 단순합니다. 에이전트가 무거울수록 실패 지점이 많아지고 디버깅이 어렵습니다. 그의 철학은 "에이전트를 최대한 작게 유지하되, 필요할 때만 확장한다"는 것입니다. 이것은 Claude Code 자체를 반대하는 게 아니라, 과도한 기능 추가에 대한 경계입니다. 와당탕 ERP 에이전트를 설계할 때도 같은 원칙이 적용됩니다: 처음부터 복잡하게 만들지 말고, 4개 도구로 시작해서 필요한 것만 더하는 방향.

### 4. 개인 워크플로우를 오픈소스로 공개 — 2026년 7월의 역설

이달 가장 주목해야 할 움직임입니다. David는 X에 이렇게 썼습니다:

> *"I'm releasing all my personal agent skills publicly for free. This represents hundreds of hours of trial and error."*

그리고 GitHub에 `davidondrej/skills` 레포를 MIT 라이선스로 공개했습니다. 설치 명령어:

```bash
npx skills add davidondrej/skills
```

카테고리: `agent-orchestration`, `research-and-web`, `thinking-and-docs`, `skill-authoring`, `ops-and-setup`

주목할 스킬: `agent-self-scheduling` — 에이전트가 자신의 다음 실행을 스스로 스케줄링합니다. `delegating-to-agents`, `handoff` — 멀티에이전트 위임 패턴. 2주 만에 2,493개 스타를 받았습니다.

**왜 무료로 공개했을까요?** 역설처럼 보이지만 전략이 명확합니다. 워크플로우를 공개하면 (a) 신뢰가 생기고, (b) 커뮤니티가 이를 발전시키며, (c) 정작 진짜 가치인 "David와 직접 일하기"(Scale Software AI, $200K+ ARR 대상 엑셀러레이터)의 문턱은 더 높아집니다. 정보는 공짜이지만 실행 능력과 1:1 접근권은 유료입니다. 이것이 그의 비즈니스 모델 핵심입니다.

---

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: `npx skills add davidondrej/skills` 로 스킬 패키지 설치 후 `skills/agent-orchestration/agent-self-scheduling` 파일 열어서 핵심 패턴 1줄 읽기. 비서앱 일정 에이전트 프롬프트에 "다음 실행 시점을 스스로 제안하는" 패턴 1줄 붙여넣기.

**이번 주 1-2시간 (mid)**: `agent-orchestration` 카테고리 전체 읽고, 와당탕 ERP의 "발주 에이전트 → 재고 에이전트 → 정산 에이전트" 핸드오프 흐름을 `handoff` 스킬 패턴으로 재설계해보기. 코드 스니펫 예시:

```bash
# 비서앱 agent_pipeline에 적용할 수 있는 handoff 패턴
# 발주완료 → 재고체크 에이전트로 자동 위임
RESULT=$(claude -p "발주 처리 완료. 재고 에이전트에게 핸드오프: {{order_id}}")
```

**이번 달 실험 (macro)**: Pi 에이전트 방식으로 비서앱 내부 에이전트 1개를 리팩터링. 현재 쓰는 도구가 몇 개인지 세어보고, 4개 이하로 줄일 수 있는지 실험. 측정 지표: 에이전트 실패율, 디버그 소요 시간.

---

## 한국 솔로 운영자 맥락에서 주의

**1. "바이브 코딩으로 $10K MRR" 수치를 그대로 복사하면 위험합니다.** David가 빠르게 SaaS를 만들 수 있는 이유는 이미 수십 개의 빌딩 실패 경험이 있기 때문입니다. Vectal.ai 이전에 수많은 실패 제품이 있었고, AI 코딩 도구가 그 실행 속도를 높여줬을 뿐입니다. 와당탕은 이미 실제 운영 맥락(발주, 재고, 예약, 정산)이 있으므로, 새로운 SaaS를 시작하는 것보다 기존 맥락에 에이전트를 이식하는 방향이 훨씬 현실적입니다.

**2. 커뮤니티 수익화 모델은 한국에서 다르게 작동합니다.** New Society $37/월 × 400명 = 월 $14,800의 수익이지만, 이것은 영어 콘텐츠로 글로벌 시장을 겨냥한 결과입니다. 한국어 커뮤니티는 규모가 작고 가격 저항이 높습니다. 강의나 커뮤니티보다는 B2B 컨설팅(AX 전환 지원)이나 도구 라이선스 모델이 더 맞을 수 있습니다.

---

## 더 깊이 보려면

- [davidondrej/skills GitHub](https://github.com/davidondrej/skills) — 실제 스킬 코드 직접 확인
- [David Ondrej YouTube](https://www.youtube.com/@DavidOndrej) — "Build Everything with AI Agents" 플레이리스트
- [New Society (Skool)](https://www.skool.com/new-society/about) — 커뮤니티 구조 참고
- [David Ondrej X(@DavidOndrej1)](https://x.com/DavidOndrej1) — 실시간 피벗 공개 채널

---

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "유튜브로 에이전트 강의를 보면 알겠는데 막상 내 비즈니스에 붙이려면 막막하다." 그 간격이 David가 파는 것임.
- **숫자**: 구독자 39만 / 누적 2,400만 뷰 / Vectal.ai 24억 엑싯 / `davidondrej/skills` 2주 만에 2,493 스타 / New Society 월 $37에 400명.
- **삽질**: Claude Code에 너무 많은 MCP를 붙이다가 Pi의 4개 도구 미니멀리즘으로 공개 피벗한 사례. "에이전트는 가벼울수록 강하다."
- **훅**: "당신이 쓰는 에이전트 도구가 몇 개인지 세어보세요. 만약 4개를 넘는다면, 오늘 David의 피벗 사례를 들어야 합니다."
