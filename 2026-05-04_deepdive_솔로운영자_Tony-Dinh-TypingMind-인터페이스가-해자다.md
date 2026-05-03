---
date: 2026-05-04
category: 솔로운영자
subject: Tony Dinh — TypingMind, 인터페이스가 해자다
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱(hyein-daily) 메모 화면 열어서 현재 쓰는 AI 채팅 UI(ChatGPT/Claude)에서 가장 불편한 점 1개를 메모에 기록하고, 그걸 해결하는 커스텀 UI가 있다면 얼마를 낼 의향이 있는지 숫자로 적기
---

# Tony Dinh — "모델은 상품이다, 인터페이스가 해자다"

## 누구/무엇인가

Tony Dinh(@tdinh_me)는 베트남 출신의 솔로 소프트웨어 개발자로, 7년간 회사 개발자로 일하다 2021년 연봉 $105K 직장을 박차고 인디 해커로 전향했다. 이후 Black Magic(트위터 애널리틱스)을 $14K MRR까지 키웠지만 일론 머스크의 트위터 API 가격 인상으로 2023년 $128K에 매각했다. 같은 해 1월, ChatGPT의 느리고 불편한 UI를 견디다 못해 하루 만에 TypingMind를 직접 만들었다. TypingMind는 출시 7일 만에 $22K 매출을 찍었고, 2024년 11월 누적 $1M을 돌파했으며, 2025년 10월 기준 월 $130~160K(연 환산 $1.6M 이상)를 버는 회사가 됐다. 직원은 여전히 0명, 프리랜서 몇 명과 함께 주 20시간만 일하면서 아내와 함께 세계 여행 중이다.

## 무엇이 특별한가

**1. "하루 만에 MVP, 7일 만에 $22K" — 빠른 출시가 전략 그 자체다**

Tony는 ChatGPT UI를 쓰면서 느낀 불편함(응답 느림, 대화 저장 불가, 멀티모델 지원 없음)을 혼자 해결하기로 했다. 첫 버전 개발 시간: 1일. 론칭 7일 후 매출: $22K. 그는 이를 "부끄러울 정도로 빨리 내놓고, 실제 사용자가 다음을 알려주게 한다(ship before it embarrasses you, let real users tell you what to do next)"로 설명한다. 1년 안에 171개 업데이트를 배포한 것도 같은 맥락이다. 완벽한 제품을 기다리는 게 아니라, 출시 자체가 데이터 수집 방법이다.

**2. 컨슈머 → B2B 피벗 없이 피벗 — 같은 제품, 다른 패키징**

TypingMind는 처음엔 개인 사용자 대상 일회성 구매(라이프타임 라이선스) 모델이었다. 그런데 어느 순간 기업들이 팀 단위로 쓰고 싶다는 문의를 보내기 시작했다. Tony는 제품을 뜯어고치지 않고 "TypingMind for Teams"라는 B2B 구독 플랜을 씌웠다. 2025년 10월 기준 B2B 팀 버전의 구독 매출이 전체의 50% 이상을 차지한다. 제품은 그대로인데 패키징을 달리해서 ARR의 절반을 안정적인 반복 매출로 전환한 것이다. 여기에 리셀러 모델도 추가했다 — 현지 컨설팅 회사가 Tony의 플랫폼 위에 자사 서비스(교육, 온보딩, 컨설팅)를 올려 팔고, Tony는 플랫폼 수수료를 받는다.

**3. 소셜 노이즈가 아니라 제품 노이즈로 성장**

TypingMind 초기 성장의 핵심은 광고도, 바이럴 콘텐츠도 아니었다. Product Hunt 론칭과 Hacker News 포스팅 2개가 초기 트래픽의 대부분을 가져왔다. 그 이후 성장은 순전히 "ChatGPT 대안 UI"를 검색하는 사람들의 SEO 유입이었다. Tony는 마케팅에 시간을 최소화하고 "제품이 스스로 바이럴 되도록" 171번 업데이트를 밀었다. 팔로워 수나 콘텐츠 조회수보다 제품 업데이트 속도가 성장 지표였다.

**4. 인프라 비용 월 $20 — 솔로의 경제학**

Tony의 기술 스택: 코딩은 Claude(AI), 백엔드는 Supabase, 배포는 Vercel, 인증은 Clerk, CDN은 Cloudflare, 벡터DB는 Pinecone. 월 $130K를 버는 회사의 인프라 비용이 $20 수준이다. "1인 회사는 팀을 유지하는 오버헤드가 없기 때문에, 커뮤니케이션에 낭비할 시간이 없다. 무엇을 자를지, 어떤 기술 부채를 감수할지 내가 즉각 결정한다(By going solo, I save a lot of time collaborating and communicating—I know which features to cut and which tech debt to take)"고 직접 말한다. 이 구조 덕분에 $1M ARR이어도 재무적 압박이 없고, 수익의 대부분이 잉여현금이 된다.

**5. "모델은 상품, 인터페이스가 해자" — 2023년에 이미 간파한 것**

Tony가 TypingMind를 만든 시점은 ChatGPT가 막 터진 2023년 1월이었다. 당시 모두가 "새 모델"을 만드는 데 집중할 때, 그는 "모델은 어차피 빨리 상품화된다. 사람들이 매일 쓰는 인터페이스가 진짜 해자다"라는 것을 자신의 불편함에서 직관했다. 2025년 현재 OpenAI, Anthropic, Google 모두 자체 모델을 갖고 있지만, TypingMind는 모든 모델을 한 인터페이스에서 쓸 수 있다는 이유로 월 $130K를 벌고 있다. 멀티모델 시대의 "인터페이스 레이어 전략"을 가장 빨리 실행한 사례다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱(hyein-daily) 메모 화면 열어서 현재 쓰는 AI 채팅 UI(ChatGPT/Claude)에서 가장 불편한 점 1개를 메모에 기록하고, 그걸 해결하는 커스텀 UI가 있다면 얼마를 낼 의향이 있는지 숫자로 적기

**이번 주 1-2시간 (mid)**: 와당탕연구소 ERP의 AI 채팅 인터페이스(wadangtang-erp) 안에 "멀티모델 전환 드롭다운"을 추가하는 프로토타입 제작. Claude SDK와 OpenAI SDK를 provider 패턴으로 감싸면 된다.

```typescript
// lib/ai-provider.ts
type Provider = 'claude' | 'gpt4o' | 'gemini';

export async function chat(provider: Provider, messages: Message[]) {
  if (provider === 'claude') {
    return anthropic.messages.create({ model: 'claude-sonnet-4-6', messages });
  }
  if (provider === 'gpt4o') {
    return openai.chat.completions.create({ model: 'gpt-4o', messages });
  }
  // ...
}
```

UI: `<select>` 컴포넌트 1개 + provider 상태 전역 관리 → 기존 채팅 컴포넌트에 `provider` props 추가. 1-2시간이면 충분.

**이번 달 실험 (macro)**: 비서앱 또는 ERP 내부에서 "AI 채팅 인터페이스 커스터마이징" 기능을 외부에 화이트라벨로 제공하는 파일럿 검토. 성공 기준: 주변 1인 사업자 3명 이상에게 시연 후 "월 3만 원 이상 낼 의향 있다"는 반응 2명 이상. TypingMind처럼 처음엔 일회성 구매(라이프타임 $49~99)로 시작해도 충분.

## 한국 솔로 운영자 맥락에서 주의

**영어권 검색 SEO vs. 한국어 생태계**: Tony의 성장 엔진은 "ChatGPT alternative UI" 같은 영어 키워드의 Google SEO였다. 한국 시장에서는 네이버 블로그/카페 유입, 카카오톡 지인 공유, 유튜브 쇼츠가 훨씬 강하다. 같은 제품을 만들더라도 "검색 유입 → 개인 결제" 퍼널보다 "콘텐츠 → 오픈카톡/커뮤니티 → 그룹 구매" 퍼널이 더 현실적이다. SEO보다 커뮤니티 중심 초기 배포 전략이 필요하다.

**B2B 컴플라이언스 비용**: Tony는 SOC2, HIPAA, GDPR 인증에 $20K 이상을 투자했다. 이게 글로벌 B2B 매출의 문을 열었다. 한국 기업 대상 B2B를 한다면 개인정보보호법, ISMS 인증 이슈가 다르게 작동한다. 한국 중소기업은 이런 인증보다 "대표의 신뢰"와 "카카오워크 연동 여부"가 구매 결정에 더 크게 작용한다. 글로벌 컴플라이언스보다 한국 특화 통합(카카오, 네이버 클라우드)에 먼저 투자하는 것이 현실적이다.

## 더 깊이 보려면

- [Tony Dinh's Newsletter (뉴스레터 아카이브)](https://news.tonydinh.com/archive)
- [My Indie Book — 70가지 인디 해커 교훈](https://news.tonydinh.com/p/early-bird-license-of-my-new-product)
- [TypingMind 팀 플랜](https://custom.typingmind.com/pricing)
- [인디 해커스 인터뷰 — $10K/mo 달성기](https://www.indiehackers.com/post/how-a-tool-that-improves-the-ui-for-chatgpt-reached-10k-mo-only-a-few-months-after-launch-5e69b67949)
- [The Bootstrapped Founder — Tony Dinh 에피소드](https://thebootstrappedfounder.com/tony-dinh-ups-and-downs-of-an-indie-hacker-journey/)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: 2023년 1월, Tony는 ChatGPT를 쓰다 너무 느리고, 대화를 저장할 수 없고, 다른 모델로 전환이 안 된다는 점에 매일 짜증났다. 누군가 해결해 주길 기다리다 "내가 이걸 직접 만들면 되겠다"는 생각으로 하루 만에 초안을 완성했다. 그 짜증이 월 $130K짜리 사업의 출발점이었다.

- **숫자**: 월 인프라 비용 $20로 월 매출 $150K(약 75배 레버리지). 직원 1명을 고용하면 이 레버리지가 즉시 무너진다 — 최소 $5K/월 인건비가 생기고, 커뮤니케이션 비용이 추가되고, 결정 속도가 절반으로 줄어든다. 솔로로 유지하는 것 자체가 수익성의 핵심이다.

- **삽질**: Black Magic은 $14K MRR까지 키웠지만, 일론 머스크가 트위터 API 가격을 대폭 올린 순간 사업 모델 전체가 흔들렸다. Tony는 "외부 플랫폼 API에 의존하는 비즈니스는 그 플랫폼이 정책을 바꾸는 순간 인질이 된다"는 교훈을 얻었다. TypingMind는 의도적으로 어떤 단일 AI 모델 제공사에도 종속되지 않게 멀티모델 구조로 설계됐다.

- **훅**: "혼자서 연 $1.6M을 버는 회사가 인프라에 쓰는 돈은 한 달에 $20입니다. 그런데 이 회사의 가장 큰 위협은 경쟁자가 아니라, 직원을 한 명 뽑는 순간입니다."
