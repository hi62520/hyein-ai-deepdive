---
date: 2026-11-17
category: AI네이티브회사
subject: "Vercel 2026 — 에이전트가 60%를 배포하는 인프라 설계자"
tags: [AI탐구, deepdive]
starred: false
micro_action: "비서앱 ERP의 버튼 하나에 Vercel AI SDK generateText() 호출을 붙여서 간단한 텍스트 생성 엔드포인트 하나를 30분 안에 만들어보기"
---

# Vercel 2026 — 에이전트가 60%를 배포하는 인프라 설계자

## 누구/무엇인가

Vercel은 Guillermo Rauch가 2015년 창업한 프론트엔드 클라우드 플랫폼입니다. Next.js 프레임워크를 만든 회사로 가장 잘 알려져 있지만, 2026년 현재는 그 정의가 근본적으로 바뀌었습니다. 현재 기업 가치는 93억 달러, ARR은 약 3억 4000만 달러이며, Rauch는 2026년 4월 IPO 준비 의사를 공식 시사했습니다. Vercel은 하루 600만 건의 배포가 일어나는 플랫폼인데, 그중 60%가 사람이 아니라 AI 에이전트가 트리거한 배포입니다. 2026년 초만 해도 그 비율은 3%였습니다. 10개월 사이에 에이전트 배포 비율이 20배 증가한 것입니다. Rauch는 이것을 "소프트웨어가 에이전트에 의해 쓰이는 시대가 왔다"는 신호로 읽고, 플랫폼 전략 전체를 그 방향으로 재편했습니다.

## 무엇이 특별한가

**1. 에이전트를 빌더이자 고객으로 본다**

Vercel이 올해 내놓은 핵심 프레임은 하나입니다. AI 에이전트는 Vercel의 플랫폼을 *이용해서* 소프트웨어를 만들고, 동시에 그 소프트웨어를 *운영*하는 고객이기도 합니다. Rauch의 말을 그대로 옮기면: *"All of that software — it needs to go somewhere, and we think it's going to be Vercel."* (그 모든 소프트웨어는 어딘가에 올라가야 하고, 우리는 그게 Vercel일 것이라고 생각합니다.) 이것은 단순한 마케팅 메시지가 아닙니다. 60% 배포 수치가 그 전략의 현실성을 증명합니다.

**2. v0 — 비개발자를 위한 에이전트 빌더**

v0는 2024년 처음 등장했을 때 "AI로 UI 컴포넌트를 생성하는 도구"였습니다. 2026년에는 완전히 다른 제품이 됐습니다. 2025년 8월 v0.dev에서 v0.app으로 도메인을 변경하고, 2026년 2월에는 GitHub 레포지토리 전체를 임포트해서 샌드박스 런타임 안에서 편집·배포까지 할 수 있도록 전면 재설계했습니다. 2026년 8월 GA(일반 공개)된 현재의 v0는 MCP 서버를 내장하고 있어서, Cursor나 Claude Code 같은 에이전트가 v0를 도구로 호출할 수 있습니다. 사람이 프롬프트로 만든 코드가 에이전트를 통해 다시 반복·수정되는 순환 구조입니다.

**3. AI SDK 7 — 하네스(Harness)가 프레임워크가 됐다**

2026년 6월 25일 출시된 AI SDK 7의 핵심은 `HarnessAgent`입니다. 이것은 Claude Code, Codex, Pi 같은 외부 에이전트 하네스를 SDK 호환 스트림으로 감싸서, 마치 모델 호출처럼 쓸 수 있게 해주는 추상화 레이어입니다. 10월 기준으로 하네스 어댑터는 10종으로 늘어났고, Deep Agents와 OpenCode 어댑터도 추가됐습니다. 별도로 `WorkflowAgent`도 있는데, 프로세스 재시작·배포 중단·승인 대기 중에도 실행 상태가 유지되는 내구성(durable) 에이전트 실행을 지원합니다. AI SDK 6(5월 4일 출시)에서 tool approval, 완전한 MCP 지원, DevTools 패널이 더해진 데 이어, SDK 7은 에이전트 하네스 추상화로 한 단계 더 올라갔습니다.

**4. WebMCP와 프로토콜 베팅**

Rauch는 MCP(Model Context Protocol)에 대해 "super bullish"라고 공개 발언했습니다. 특히 WebMCP — 브라우저 환경에서 에이전트가 웹 인프라를 직접 활용할 수 있는 MCP 확장 — 에 대해 테슬라 FSD(완전 자율주행)에 비유하며 에이전트가 웹을 운전하는 미래의 핵심 인프라라고 설명했습니다. HTTP가 데스크톱 소프트웨어를 웹으로 가져왔듯, MCP가 앱 경계를 에이전트 중심으로 재편할 것이라는 시각입니다. Vercel이 AI Gateway, Sandbox(퍼시스턴트 파일시스템 스냅샷 지원), Workflow SDK, Chat SDK를 하나로 묶은 "Agent Stack"을 2026년 상반기에 공식화한 것도 이 맥락입니다.

**5. 1인 1조 달러 회사 테제**

Rauch가 반복적으로 언급하는 미래 그림은 "한 사람과 에이전트 팀이 조 달러 규모의 사업을 짓는 것"입니다. 이것은 단순한 미래 예측이 아니라 Vercel의 제품 전략과 직결됩니다. v0는 비개발자가 에이전트 도움으로 프로덕션 소프트웨어를 만들게 하는 도구이고, AI SDK + HarnessAgent는 개발자가 에이전트 팀을 오케스트레이션하는 런타임입니다. 두 도구 모두 "1인 운영자가 에이전트 팀을 굴리는 세상"을 타깃으로 설계돼 있습니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱 ERP의 가장 단순한 버튼 하나에 Vercel AI SDK `generateText()` 호출을 붙여서 간단한 텍스트 생성 엔드포인트 하나를 만들어보세요. npm에서 `@ai-sdk/anthropic`과 `ai` 패키지를 설치하고, 5줄짜리 API 라우트 하나로 충분합니다. 프론트엔드가 없어도 됩니다. 이 엔드포인트가 만들어지는 순간 비서앱이 Vercel AI SDK 생태계 위에 올라서는 첫 번째 발판이 됩니다.

```typescript
import { generateText } from 'ai';
import { anthropic } from '@ai-sdk/anthropic';

export async function POST(req: Request) {
  const { prompt } = await req.json();
  const { text } = await generateText({
    model: anthropic('claude-sonnet-4-5'),
    prompt,
  });
  return Response.json({ text });
}
```

**이번 주 1-2시간 (mid)**: v0.app에서 비서앱의 반복 작업 하나(예: 주간 일정 요약 뷰, 메모 카드 UI)를 프롬프트로 만들어서 GitHub에 푸시해보세요. v0가 생성한 컴포넌트를 현재 ERP 코드베이스에 붙여넣을 수 있는지 확인합니다. 에이전트가 뽑아준 코드를 내가 검토·수정하는 흐름을 한 번만 경험해도 감각이 완전히 달라집니다.

**이번 달 실험 (macro)**: AI SDK 7의 `WorkflowAgent`를 활용해서 느린호밀의 주문 → 베이킹 준비 → 픽업 알림 흐름 중 하나를 내구성 에이전트 워크플로우로 만들어 보세요. 프로세스가 중단되어도 상태가 유지되는지, 승인 대기(예: 재고 부족 시 사장님 확인) 단계를 중간에 끼울 수 있는지를 측정 지표로 삼습니다. 성공 기준: 배포 사이에도 주문 흐름이 끊기지 않는 것.

## 한국 솔로 운영자 맥락에서 주의

**Next.js 의존성 함정**: Vercel의 AI 도구들은 대부분 Next.js(또는 Vercel 플랫폼)와 가장 잘 맞습니다. 비서앱을 다른 스택으로 짜고 있다면 AI SDK 자체는 프레임워크 무관하지만, Vercel의 Sandbox, AI Gateway, Chat SDK는 Vercel 배포 환경에서 비용·속도 면에서 훨씬 유리합니다. "Vercel에 올리지 않으면 반값"이 아니라는 점을 미리 계산해두세요.

**속도와 Lock-in 사이**: 60%가 에이전트 배포라는 숫자가 인상적이지만, 그것은 Vercel이 에이전트 빌더를 플랫폼 안에 가두는 전략이기도 합니다. v0, AI SDK, Sandbox, AI Gateway를 모두 쓰기 시작하면 마이그레이션 비용이 급격히 올라갑니다. 솔로 운영자로서 "지금 빠르게 만드는 것"과 "나중에 갈아탈 수 있는 것" 사이 균형을 의식적으로 잡아야 합니다. AI SDK만큼은 오픈소스이고 다중 프로바이더를 지원하므로, 이것부터 쓰고 Vercel 고유 기능은 필요한 때에 추가하는 순서가 현명합니다.

## 더 깊이 보려면

- [Vercel AI SDK 7 공식 블로그](https://vercel.com/blog/ai-sdk-7)
- [AI SDK Harnesses 공식 문서](https://ai-sdk.dev/v7/docs/ai-sdk-harnesses)
- [Vercel CEO IPO 시그널 — TechCrunch](https://techcrunch.com/2026/04/13/vercel-ceo-guillermo-rauch-signals-ipo-readiness-as-ai-agents-fuel-revenue-surge/)
- [Vercel $9.3B 전략 분석 — Sourcery](https://www.sourcery.vc/p/breaking-93b-vercel-on-ais-infra)
- [1인 조 달러 회사 테제 — Startup Hub](https://www.startuphub.ai/ai-news/artificial-intelligence/2026/vercel-wants-one-person-and-agents-to-build-1t)
- [Vercel AI 가이드 — Agent Stack](https://vercel.com/guides/ai-agents)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: 에이전트가 코드를 짜줘도, 그 코드가 어디 올라가서 어떻게 돌아가는지 아는 사람이 없으면 프로덕션은 여전히 사람 손을 탑니다. 배포 인프라가 없는 에이전트는 그림의 떡입니다.
- **숫자**: 2026년 1월 3% → 10월 60%. 에이전트 배포 비율이 10개월 만에 20배. 하루 600만 건 배포 중 360만 건이 에이전트 트리거.
- **삽질**: v0 초기 사용자 중 많은 수가 "컴포넌트는 예쁘게 나오는데 실제 프로젝트에 붙이면 타입 오류"를 겪었습니다. 2026년 2월 재설계 이후 GitHub 레포 전체를 컨텍스트로 주는 방식으로 이 문제를 해결했는데, 이 삽질 과정이 "에이전트는 격리된 환경이 아니라 전체 컨텍스트를 알아야 한다"는 교훈을 현실로 보여줍니다.
- **훅**: "2026년 1월, Vercel 배포의 97%는 사람이 했습니다. 10개월이 지난 지금, 그 비율이 뒤집혔습니다. 당신의 비서앱은 에이전트가 배포할 준비가 됐나요?"
