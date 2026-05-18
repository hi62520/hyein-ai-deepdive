---
date: 2026-05-19
category: AI네이티브회사
subject: Vercel / Guillermo Rauch — 바이브코딩을 프로덕션으로 직행시키는 AI 클라우드
tags: [AI탐구, deepdive]
starred: false
micro_action: v0.dev에서 비서앱 대시보드 화면 하나를 프롬프트 한 줄로 생성하고, 생성된 코드를 Claude Code 프로젝트에 붙여넣어 30분 내 동작 확인
---

# Vercel / Guillermo Rauch — "바이브코딩을 프로덕션으로 직행시킨다"

## 누구/무엇인가

Vercel은 Next.js와 프론트엔드 배포 플랫폼으로 알려진 회사지만, 2024년부터는 **AI 클라우드(AI Cloud)** 전략으로 완전히 피벗했습니다. 아르헨티나 출신 CEO 기예르모 라우치(Guillermo Rauch)는 2016년 Vercel(당시 ZEIT)을 창업했고, 2026년 현재 회사는 ARR $340M, 기업가치 $9.3B(약 1.3조 원)에 달하는 AI-네이티브 인프라 기업으로 성장했습니다. 핵심 제품은 **v0.dev** — 자연어 한 줄로 프로덕션 수준의 Next.js 앱을 뽑아내는 AI 빌더로, 출시 이후 현재까지 **400만 명 이상**이 사용했습니다. 그의 비전을 한 문장으로 요약하면 "**영어가 곧 코드다(English is the new programming language)**"입니다.

## 무엇이 특별한가

### 1. 바이브코딩을 '그냥 써보기'에서 프로덕션으로 끌어올렸다

v0는 초기에 "재미있는 프로토타입 생성기"였지만, 2025년 말 라우치는 v0를 전면 재설계했습니다. 새 v0는 기존 GitHub 레포를 임포트해 환경변수와 설정을 자동으로 읽어들이고, 샌드박스 내에서 생성한 코드가 실제 Vercel 배포 환경과 1:1로 매핑됩니다. VS Code가 인터페이스 안에 내장되어 있어 브랜치 생성 → PR 오픈 → 머지 후 배포까지 v0 탭을 떠나지 않고 완료할 수 있습니다. Vercel CPO Tom Occhino는 이 문제를 **"세계 최대의 Shadow IT 문제"**라고 불렀습니다 — AI가 코드는 만들어주는데 기존 인프라에 붙이지 못하는 90% 구간.

### 2. "Anyone can cook" — 비개발자도 프로덕션 PR을 낼 수 있다

2026년 2월 Lenny's Newsletter 기고에서 라우치는 Vercel 내부 비개발자 직원들이 v0를 통해 직접 브랜치를 따고 PR을 올리는 사례를 공개했습니다. 픽사 영화 '라따뚜이'의 명대사 **"Anyone can cook(누구나 요리할 수 있다)"** 을 비유로 들며, 코딩 역량이 없는 팀원도 프로덕션 기여자가 될 수 있다고 주장했습니다. 라우치 본인은 코드 최적화를 지시할 때를 "**It was all vibes from my side. I didn't care how, it just made it faster.**"라고 표현했습니다.

### 3. 보안을 AI로 해결하는 'Secure Vibe Coding'

바이브코딩의 최대 비판은 보안입니다. 라우치는 2025년 4월 트위터에 이렇게 밝혔습니다: _"Secure vibe coding @v0 has now prevented LLMs from writing vulnerable code in **16,200+ generated applications**. Concretely, it's prevented sixteen thousand token leaks, from AI api keys to database compromises."_ v0는 서버사이드 함수를 격리된 샌드박스에서 실행하고, API 키를 암호화 볼트에 보관합니다. "AI 실수의 해독제는 더 많은 AI"라는 철학이 핵심입니다. 가장 많이 막은 유출 키는 Google Maps, Supabase 백엔드, OpenAI·Claude·Gemini 키였습니다.

### 4. AI 에이전트가 앱을 짓는 시대, 플랫폼이 되는 Vercel

Vercel 플랫폼에서 실행 중인 앱의 **30%가 이미 AI 에이전트가 배포한 것**입니다. 라우치는 TechCrunch와의 인터뷰에서 "에이전트는 엄청난 속도로 배포한다. 우리의 미래 성장은 인간 개발자뿐 아니라 에이전트 클라이언트로부터 온다"고 밝혔습니다. 실제로 ARR이 2024년 초 $100M에서 2026년 2월 $340M으로 **3.4배** 성장했으며, YoY 성장률은 84%입니다. IPO에 대해서는 "**The company's ready and getting more ready for it every day.**"라는 말로 준비 완료임을 시사했습니다.

### 5. Vercel AI SDK 6 — 솔로 개발자의 멀티에이전트 레고

오픈소스 `ai` 패키지로 배포되는 Vercel AI SDK는 2025년 6버전에서 **Agent 추상화**를 공식 도입했습니다. `ToolLoopAgent` 클래스 하나로 오케스트레이터-스페셜리스트 멀티에이전트 패턴을 구현할 수 있고, `needsApproval` 플래그 하나로 Human-in-the-loop를 붙일 수 있습니다. 단일 LLM 호출이 아니라 툴 체인 루프 전체를 관리하며, 병렬 디스패치까지 지원합니다. 이 SDK는 Next.js + Vercel 생태계와 네이티브로 통합됩니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: v0.dev에서 비서앱 대시보드 화면 하나를 프롬프트 한 줄로 생성하고, 생성된 코드를 Claude Code 프로젝트에 붙여넣어 30분 내 동작 확인. `"Create a daily task dashboard with a ledger memo input and Telegram status badge using Next.js and Tailwind"` 형태로 시작.

**이번 주 1-2시간 (mid)**: Vercel AI SDK를 비서앱의 에이전트 레이어에 연결해 보세요. 현재 Claude Code로 직접 짜고 있는 에이전트 루프를 `ai` 패키지의 `ToolLoopAgent`로 래핑하면, 툴 실행·에러 재시도·컨텍스트 관리를 프레임워크가 대신 처리합니다.

```typescript
import { ToolLoopAgent } from 'ai';
import { anthropic } from '@ai-sdk/anthropic';

const secretaryAgent = new ToolLoopAgent({
  model: anthropic('claude-sonnet-4-6'),
  instructions: '와당탕연구소 비서 에이전트. 일정·메모·ERP 작업을 처리한다.',
  tools: { createMemo, sendTelegram, updateLedger },
});

const result = await secretaryAgent.run('오늘 ledger에 deepdive 완료 기록하고 텔레그램 알림 보내줘');
```

**이번 달 실험 (macro)**: v0로 느린호밀 메뉴판·주문폼 UI를 생성 → GitHub PR로 올리기까지 전 과정을 "비개발자 아르바이트생이 할 수 있는가" 기준으로 테스트. 성공 기준: 대표님 개입 없이 직원이 메뉴 추가 UI를 혼자 프로덕션 배포. 측정 지표: PR 생성까지 소요 시간 (목표: 30분 이내).

## 한국 솔로 운영자 맥락에서 주의

**1. v0는 Next.js 생태계 의존도가 높습니다.** 현재 비서앱이 다른 프레임워크 기반이라면 v0가 생성한 코드를 그대로 쓰기 어렵습니다. 컴포넌트 수준에서 부분 발췌하거나 Claude Code로 프레임워크 변환 후 사용하는 전략이 현실적입니다.

**2. 2026년 4월 Vercel 자체 보안 사고가 있었습니다.** 서드파티 AI 플랫폼 'Context AI' 해킹으로 Vercel 직원 계정이 침해되는 사고가 발생했습니다. Vercel이 '보안 바이브코딩'을 강조하지만, 외부 의존 서비스의 공급망 리스크는 여전합니다. 비서앱·ERP의 API 키를 v0 환경변수에 넣기 전에 최소 권한 원칙(read-only 키 분리)을 적용하세요.

## 더 깊이 보려면

- [Vercel AI SDK 6 공식 발표](https://vercel.com/blog/ai-sdk-6)
- [Sequoia Capital 팟캐스트: Guillermo Rauch — Building the Generative Web](https://sequoiacap.com/podcast/training-data-guillermo-rauch/)
- [Lenny's Newsletter: "Anyone can cook" — v0 Git Workflow](https://www.lennysnewsletter.com/p/anyone-can-cook-how-v0-is-bringing)
- [Vercel Secure Vibe Coding 블로그](https://vercel.com/blog/v0-vibe-coding-securely)
- [TechCrunch: Vercel IPO 준비 + AI 에이전트 수익 급증](https://techcrunch.com/2026/04/13/vercel-ceo-guillermo-rauch-signals-ipo-readiness-as-ai-agents-fuel-revenue-surge/)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: AI가 코드를 10초 만에 생성하는데, 그걸 기존 서비스에 붙이는 데 3시간이 걸린다. 바이브코딩의 90% 구간 문제.
- **숫자**: v0.dev 사용자 400만 명. Vercel ARR $100M → $340M (2년, 3.4배). 플랫폼 앱의 30%가 이미 에이전트 배포. AI 키 유출 16,200건 방지.
- **삽질**: Guillermo 본인도 "It was all vibes from my side"라고 했다. CEO조차 어떻게 구현되는지 모른다. 중요한 건 결과가 빠르게 나오는 것.
- **훅**: "30초 만에 앱 만드는 건 쉬워졌는데, 그 앱을 실제 고객한테 보여주는 데 왜 3일이 걸릴까요?" — 이게 Vercel이 풀려는 문제입니다.
