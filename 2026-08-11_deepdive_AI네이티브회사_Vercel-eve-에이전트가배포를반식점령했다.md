---
date: 2026-08-11
category: AI네이티브회사
subject: Vercel & eve — 에이전트가 배포를 반식 점령했다
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱 에이전트 설계에 eve 방식 적용 — agents/daily-brief/ 디렉토리 만들고 instructions.md 한 장 작성해보기
---

# Vercel & eve — 에이전트가 배포를 반식 점령했다

## 누구/무엇인가

Vercel은 프론트엔드 개발자라면 누구나 아는 클라우드 배포 플랫폼입니다. Next.js를 만든 회사이기도 하고, "배포는 Vercel"이라는 공식이 스타트업 생태계에서 2020년대 초반부터 당연한 상식이 됐습니다. CEO Guillermo Rauch는 아르헨티나 출신 개발자로, 프론트엔드 인프라를 민주화하는 것을 회사의 핵심 명제로 삼아왔습니다.

2026년 현재, Vercel은 제2의 전환점을 맞이했습니다. 그들은 이제 "AI 네이티브 배포 플랫폼"을 선언하고 있고, 숫자가 그 선언을 뒷받침합니다. ARR은 2024년 초 $1억에서 2026년 2월 기준 $3억 4천만 런레이트로 3.4배 성장했습니다. Series F 투자로 기업가치 $93억을 인정받았고, Guillermo는 2026년 IPO 준비 신호를 공개적으로 내비쳤습니다.

그런데 진짜 숫자는 따로 있습니다. Vercel의 일일 배포 건수는 600만 건인데, 그 중 절반 이상이 이제 코딩 에이전트에 의해 트리거됩니다. 6개월 전만 해도 3% 미만이었습니다.

## 무엇이 특별한가

**1. 배포 패러다임의 교체 — 인간 → 에이전트**

Vercel이 공개한 가장 충격적인 수치는 이것입니다: 6개월 전 에이전트 트리거 배포 비율 < 3% → 2026년 6월 50%+. AI Gateway를 통과하는 월간 토큰 처리량도 같은 기간 2조 → 20조 토큰으로 10배 늘었습니다. Rauch는 이를 "generative web" 전환으로 명명합니다. 앱이 인간이 아니라 에이전트에 의해 만들어지고, Vercel은 그 앱들이 착지하는 곳이라는 뜻입니다. 플랫폼에서 실행되는 앱의 30%가 이미 에이전트 기원(agent-originated)이라는 사실은 이 전환이 먼 미래 얘기가 아님을 보여줍니다.

**2. eve — "에이전트를 위한 Next.js"**

2026년 6월 17일 런던 Ship 컨퍼런스에서 발표된 eve 프레임워크가 핵심입니다. 컨셉은 단순하고 강력합니다: **에이전트는 디렉토리다.** `agent/` 폴더 하나를 만들고, Markdown으로 지침과 스킬을 정의하고, TypeScript로 도구를 작성하면 — Vercel Functions 위에서 내구성 있게 실행되는 프로덕션 에이전트가 됩니다. 빌트인으로 포함된 기능이 인상적입니다: 내구 실행(durable execution), 샌드박스 컴퓨트, 휴먼 승인 스텝, 서브에이전트, 이발(evals), 멀티채널 배포(GitHub·Slack·Salesforce·Notion·Linear). 배포 채널을 바꿔도 에이전트 코어 로직은 건드리지 않아도 됩니다.

특히 인상적인 것은 **휴먼-인-더-루프 승인**입니다. 에이전트가 민감한 액션을 취하기 전 일시 정지하고, 승인이 날 때까지 컴퓨트 낭비 없이 무기한 대기합니다. 비용도 안 쓰고 신뢰도 챙기는 설계입니다.

**3. Agent Stack — 에이전트 인프라의 단일화**

eve는 홀로 등장하지 않았습니다. Vercel은 같은 날 **Agent Stack**을 발표했는데, 이는 기존 제품들을 에이전트 워크플로에 맞게 통합한 것입니다: AI SDK + AI Gateway + Vercel Sandbox + Workflow SDK + Chat SDK + 신규 Vercel Connect. Vercel Connect는 기존의 수명이 긴 자격증명(long-lived credentials)을 단기 스코프 토큰으로 대체하여 에이전트가 권한 밖에서 행동하는 것을 막는 엔터프라이즈 보안 레이어입니다. Slack, GitHub, Snowflake, Salesforce, Notion, Linear와 처음부터 통합됐습니다.

**4. 모델 라우팅 + 관측가능성 — AI Gateway의 진화**

Vercel의 AI Gateway는 단순 프록시가 아닙니다. 2026년 7월 보고서에 따르면, Gateway를 통한 오픈웨이트 모델 트래픽이 전체의 29%에 달하며, 토큰당 가격은 평탄화 추세입니다. Vercel은 모델 라우팅, 격리 컴퓨트, 태스크 오케스트레이션, 관측가능성을 한 플랫폼에서 제공하려는 것입니다. 에이전트 개발에 필요한 인프라를 조각조각 조립하지 않아도 되는 구조를 만들겠다는 뜻입니다.

**5. IPO를 향한 비즈니스 서사**

Rauch는 2026년 4월 IPO 준비를 공개적으로 언급했습니다. ARR $3.4억, 배포 600만 건/일, 에이전트 배포 50%+ — 이 숫자들은 단순한 성장이 아니라 "에이전트 경제의 기반 인프라"라는 새로운 카테고리를 입증하는 근거로 쓰이고 있습니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱 에이전트 설계에 eve 방식 적용 — `agents/daily-brief/` 디렉토리를 로컬에 만들고 `instructions.md` 한 장 작성해보기. "에이전트 = 디렉토리"라는 구조 사고를 내면화하는 것이 핵심.

**이번 주 1-2시간 (mid)**: 현재 비서앱의 에이전트 로직 중 "승인이 필요한 액션"이 무엇인지 목록화. 예를 들어 — 외부 발주 확인, 고객 자동 응답 발송, ERP 재고 입력. 각 액션에 "휴먼 승인 게이트" 한 개씩 설계. 코드 스니펫:

```typescript
// eve 방식 승인 패턴을 비서앱 ERP에 이식
const APPROVAL_REQUIRED_ACTIONS = [
  'send_customer_message',
  'create_purchase_order',
  'update_inventory_bulk',
] as const;

async function executeWithApproval(action: typeof APPROVAL_REQUIRED_ACTIONS[number], payload: unknown) {
  const pendingId = await db.approvals.create({ action, payload, status: 'pending' });
  // Telegram 알림 → 대표님 승인 버튼 → 재개
  await notifyForApproval(pendingId);
  return pendingId; // 승인 대기, 컴퓨트 낭비 없이 종료
}
```

**이번 달 실험 (macro)**: 와당탕 비서앱에 "에이전트 레지스트리" 만들기. `agents/` 폴더 하위에 daily-brief, inventory-check, customer-reply 세 가지 에이전트를 각각 디렉토리로 분리. 각 디렉토리에 `instructions.md` + `tools.ts` 두 파일만으로 정의. 측정 지표: 에이전트당 평균 승인 대기 시간, 오류 액션 발생률.

## 한국 솔로 운영자 맥락에서 주의

**스택 종속성 문제**: eve와 Vercel Agent Stack은 강력하지만, Vercel 생태계에 깊이 들어갈수록 탈출 비용이 높아집니다. 특히 Vercel Connect의 단기 토큰 구조는 Vercel의 인프라와 강하게 결합됩니다. 한국 솔로 운영자 대부분은 이미 AWS나 국내 클라우드를 쓰고 있어, 마이그레이션 비용 대비 실익을 먼저 계산해야 합니다. eve의 **파일 기반 에이전트 설계 철학**만 빌려와서 현재 스택에 이식하는 것이 더 실용적입니다.

**6백만 배포/일은 참고용 숫자**: Vercel의 성장은 주로 글로벌 SaaS 스타트업과 엔터프라이즈 덕분입니다. 국내 솔로 운영자 맥락에서 "에이전트 배포 50%"를 곧이곧대로 받아들이면 과대 투자로 이어집니다. 지금 당장은 비서앱에 에이전트 1-2개 붙여서 실제 운영 시간을 줄이는 것이 현실적입니다.

## 더 깊이 보려면

- [Vercel Ship 2026: Agents Now Drive Half of Deployments](https://www.digitalapplied.com/blog/vercel-ship-2026-agents-half-of-deployments-enterprise-stack)
- [Introducing eve, an open-source agent framework (Vercel Changelog)](https://vercel.com/changelog/introducing-eve-an-open-source-agent-framework)
- [Vercel launches eve — treats agents as directories (The New Stack)](https://thenewstack.io/vercel-launches-eve-an-open-source-framework-that-treats-agents-as-directories/)
- [Vercel CEO Guillermo Rauch — AI agent strategy details (The AI Insider, July 2026)](https://theaiinsider.tech/2026/07/09/vercel-ceo-guillermo-rauch-details-ai-agent-strategy-as-coding-and-internal-automation-emerge-as-key-use-cases/)
- [Vercel AI Gateway Production Index — July 2026](https://vercel.com/blog/ai-gateway-production-index-july-2026)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: AI 에이전트를 만들었는데, 에이전트가 권한 밖에서 막 행동해서 실서비스에서 장애가 났다. 아무도 멈출 수 없었다. Vercel이 Passport와 Connect로 공략하는 정확히 그 고통.
- **숫자**: 6개월 만에 에이전트 트리거 배포 3% → 50%. AI Gateway 토큰 처리량 2T → 20T/월. ARR $1억 → $3.4억 런레이트. 이 세 개 숫자는 단순 성장이 아니라 플랫폼 전환의 증거다.
- **삽질**: Vercel은 원래 "프론트엔드 전문"이라는 포지션 때문에 백엔드·에이전트 쪽으로 확장할 때 내부 저항이 있었다고 한다. eve는 그 경계를 문서 한 장(Markdown)으로 허물었다.
- **훅**: "하루 600만 번 앱이 배포되는 플랫폼이 있는데, 그 중 절반은 사람이 버튼을 누른 게 아닙니다. 에이전트가 했습니다. 6개월 전에 그 비율은 3%였습니다."
