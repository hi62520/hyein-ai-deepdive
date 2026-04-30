---
date: 2026-05-01
category: 에이전트빌딩
subject: David Ondrej — 에이전트-to-소프트웨어 전략
tags: [AI탐구, deepdive]
starred: false
micro_action: 옵시디언에서 '에이전트-소프트웨어-후보.md' 노트 생성 후, 와당탕/느린호밀 운영 중 가장 반복적인 작업 3개를 적고 "외부에 $37/월로 팔 수 있을까?" 질문으로 각 항목 평가 메모 추가
---

# David Ondrej — "SaaS는 죽었다. 에이전트가 죽였다"

## 누구/무엇인가

David Ondrej는 체코 출신 AI 기업가이자 YouTuber로, 채널 @DavidOndrej에서 321K 구독자를 보유하고 있습니다. 원래 게임 유튜브 채널로 월 $20,000를 벌다가 알고리즘 변화로 수익이 $600으로 급락했고, 2023년 말 AI로 완전히 피벗했습니다. 이후 Skool 커뮤니티 'New Society'로 월 $45,000 수익을 만들고, 2024년 10월 AI 생산성 앱 Vectal.ai를 창업해 단 14개월 만에 $1,800,000(약 24억 원)에 AgentZero에 매각했습니다. 현재는 AgentZero의 CEO를 맡으면서, AI 창업자를 위한 스타트업 액셀러레이터 'Scale Software AI'를 운영하고 있습니다. 그의 핵심 주장은 단 한 줄 — "SaaS is dead. Agents killed it."

## 무엇이 특별한가

**1. 게임 채널 붕괴 → AI 피벗 → 14개월 만에 $1.8M 엑싯**

David의 게임 YouTube 채널은 최전성기에 월 $20,000를 벌었습니다. 그러나 어느 날 알고리즘이 바뀌면서 수익이 $600으로 곤두박질쳤습니다. 이 경험이 그를 AI로 밀어 넣었습니다. 그는 n8n 자동화 튜토리얼을 시작으로 AI 에이전트 분야에 진입했고, 'New Society'라는 Skool 커뮤니티($37/월)로 400명 이상의 멤버를 모아 안정적인 반복 수익을 만들었습니다. 2024년 10월 창업한 Vectal.ai는 AI 기반 태스크 자동화 앱으로, 2025년 4월 $155,000 ARR을 달성했습니다. 2025년 12월 Vectal을 AgentZero에 $1,800,000에 매각 — 창업 14개월 만의 엑싯입니다. ARR 대비 약 11.6배 멀티플입니다.

**2. "SaaS는 죽었다" — 에이전트가 기존 모델을 잠식하는 논리**

David가 X(트위터)에 올린 "SaaS is dead. Agents killed it."이라는 문장은 단순한 도발이 아닙니다. 그의 논리는 이렇습니다: 기존 SaaS의 해자(moat)는 "예쁜 UI + API 통합 + 사용자당 과금"에 불과했습니다. 그런데 에이전트가 등장하면서 "예쁜 UI + 통합"은 하루 만에 복제 가능해졌습니다. 반면 에이전트 기반 소프트웨어는 사용자의 데이터와 워크플로에 깊숙이 결합되어 전환 비용(switching cost)이 훨씬 높습니다. 즉, 살아남는 소프트웨어는 '기능'이 아니라 '자동화된 업무 결과'를 판매하는 것이라는 주장입니다. 이 관점은 Shopify의 Tobi Lütke, Klarna의 전략과 같은 맥락입니다.

**3. 에이전트-to-소프트웨어(Agent-to-Software) 전략**

David의 핵심 방법론은 '에이전트를 먼저 만들고, 그걸 소프트웨어로 포장해 팔아라'입니다. Scale Software AI($8,000짜리 액셀러레이터)에서 가르치는 내용의 핵심이 바로 이것입니다. 1단계: n8n이나 Claude 같은 도구로 특정 반복 업무를 처리하는 에이전트를 만든다. 2단계: 그 에이전트를 감싸는 최소한의 UI와 온보딩을 붙인다. 3단계: SaaS처럼 월정액으로 판다. Vectal이 정확히 이 방식으로 만들어졌습니다. "에이전트 하나가 곧 제품 하나"라는 사고방식입니다.

**4. 멀티에이전트 YouTube 프리프로덕션 시스템**

David는 자신의 YouTube 콘텐츠 제작에도 멀티에이전트를 적용했습니다. 구체적으로: 에이전트 1이 영상 주제를 리서치하고 스크립트 구조를 제안하면, 에이전트 2가 OpenAI 이미지 API를 써서 썸네일 시안을 생성합니다. 이 두 에이전트는 n8n 워크플로로 연결되어 있어 사람이 개입하는 구간이 최종 검토뿐입니다. 321K 채널을 혼자 주 2회 업로드로 유지하면서 이런 시스템을 쓴다는 건 솔로 오퍼레이터에게 직접적인 레퍼런스입니다.

**5. 수익 레이어를 3개로 분리한 포트폴리오 구조**

David는 수입원을 하나에 의존하지 않았습니다: YouTube 광고 수익(변동성 높음) + New Society 커뮤니티($37/월 구독, 예측 가능) + Scale Software AI 액셀러레이터($8,000 고가 프로그램, 소수 정예). 이 구조는 Daniel Vassallo의 '포트폴리오 베팅' 개념과 정확히 맞닿아 있습니다. 어느 하나가 흔들려도 나머지가 받쳐주는 구조입니다. 그리고 그 위에 Vectal 엑싯이라는 일회성 큰 수익이 얹혔습니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 옵시디언에서 `에이전트-소프트웨어-후보.md` 노트를 새로 만들고, 와당탕연구소와 느린호밀 운영 중 가장 반복적인 작업 3가지를 목록으로 적습니다. 각 항목 아래 "이걸 n8n 에이전트로 만들면 비슷한 고통을 가진 다른 사업자에게 월 37,000원에 팔 수 있을까?"라고 자문하고 YES/NO와 이유를 한 줄씩 메모합니다. 이게 frontmatter `micro_action`과 동일합니다.

**이번 주 1-2시간 (mid)**: 와당탕 ERP(wadangtang-erp)에서 가장 반복적인 업무 하나(예: 주문 확인 → 재고 차감 → 알림 발송)를 n8n 무료 자가호스팅으로 에이전트화합니다. n8n의 AI Agent 노드에 Claude API를 연결하고, Telegram 트리거(대표님 메시지 수신) → 에이전트 처리 → Telegram 응답으로 이어지는 3노드 워크플로를 완성합니다. 참고 코드: n8n에서 AI Agent 노드를 드래그한 뒤 'Tools' 섹션에 HTTP Request 노드(wadangtang-erp API 엔드포인트)를 연결하는 방식입니다.

```json
{
  "nodes": [
    { "type": "n8n-nodes-base.telegramTrigger", "name": "Trigger" },
    { "type": "@n8n/n8n-nodes-langchain.agent", "name": "AI Agent",
      "parameters": { "systemMessage": "당신은 와당탕연구소 ERP 비서입니다." } },
    { "type": "n8n-nodes-base.telegram", "name": "Reply" }
  ]
}
```

**이번 달 실험 (macro)**: 위 에이전트 워크플로를 '외부 테스트'에 노출합니다. 지인 소규모 사업자 1명에게 "우리 비서앱 일부 기능 베타 써볼래요?"라며 Telegram 채널 링크를 공유합니다. 4주 후 측정 지표: 일주일에 몇 번 사용했는가, 어떤 기능을 가장 많이 쓰는가, 월 37,000원 내겠다는 응답이 나오는가. 성공 기준: 베타 사용자 1명이 "이거 계속 쓰고 싶다"라고 말하면 패키징 가치 있음.

## 한국 솔로 운영자 맥락에서 주의

**엑싯 멀티플은 미국 시장 기준입니다.** Vectal의 $155K ARR에 $1.8M(11.6배)을 붙인 건 미국 AI 스타트업 M&A 시장의 거품과 에이전트 테마 프리미엄이 복합된 결과입니다. 한국 SaaS/에이전트 제품의 M&A 시장은 훨씬 작고, 같은 ARR 대비 배수를 기대하기 어렵습니다. "빠른 빌드 후 엑싯" 전략을 그대로 따라 하기보다, 장기적으로 반복 수익(MRR)을 쌓는 구조에 집중하는 게 한국 솔로 오퍼레이터에게 현실적입니다.

**n8n 에이전트의 한국어 처리 한계.** David의 워크플로는 영어 기반 LLM 프롬프트와 영어 커뮤니티를 전제합니다. 와당탕/느린호밀처럼 한국어 고객 대응이 필요한 경우, Claude Sonnet이나 GPT-4o의 한국어 능력은 충분하지만 n8n 내 한국어 특화 노드나 한국 결제 API(스마트스토어, 카카오페이 등) 연동은 직접 커스텀 HTTP Request 노드로 구성해야 합니다. David의 튜토리얼을 참고할 때 "영어 노드명 → 한국 API 엔드포인트로 교체"하는 번역 작업이 추가로 필요합니다.

## 더 깊이 보려면

- [David Ondrej YouTube @DavidOndrej](https://www.youtube.com/@DavidOndrej)
- ["I Built an AI Startup Using ONLY AI Agents" — YouTube](https://www.youtube.com/watch?v=qA0CQchUydY)
- ["I sold my AI startup for $1,800,000 – here's why" — YouTube](https://www.youtube.com/watch?v=zocqnx1vx1E)
- [Build Everything with AI Agents: Here's How — YouTube](https://www.youtube.com/watch?v=XVO3zsHdvio)
- [Scale Software AI 리뷰 — ippei.com](https://ippei.com/scale-software-ai/)
- [David Ondrej on X @DavidOndrej1](https://x.com/DavidOndrej1)
- [New Society — Skool 커뮤니티](https://www.skool.com/new-society/about)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: David의 게임 채널은 매달 $20,000를 벌었습니다. 그런데 알고리즘이 하루아침에 바뀌면서 수익이 $600으로 추락했습니다. 플랫폼 한 곳에 의존한 솔로 크리에이터가 느끼는 공포 — "내 매출이 내 결정이 아니다" — 가 그를 에이전트 빌더로 바꾼 계기입니다.

- **숫자**: Vectal.ai는 창업 6개월 만에 $155,000 ARR, 14개월 만에 $1,800,000에 매각됐습니다. 1인 창업자가 Claude/n8n 기반으로 만든 앱이 한국 돈으로 약 24억 원에 팔린 겁니다. 이게 가능한 이유는 ARR보다 "에이전트 기술 + 커뮤니티 + 브랜드"의 번들 가치를 인수자가 샀기 때문입니다.

- **삽질**: David는 초창기 AI 에이전트 튜토리얼을 올릴 때 "이건 너무 기술적이라 일반인은 못 따라 한다"는 댓글을 많이 받았습니다. 그가 선택한 해법은 복잡한 코드 대신 n8n 노드를 드래그하는 no-code 영상으로 접근을 낮추는 것이었습니다. 결과적으로 이 결정이 321K 구독자를 만든 핵심이었습니다 — 코드를 모르는 사람도 에이전트를 만들 수 있다는 신호가 된 것입니다.

- **훅**: "게임 유튜버가 14개월 만에 24억짜리 AI 회사를 팔았습니다. 그는 개발자가 아니었습니다. n8n이라는 드래그앤드롭 툴과 Claude API 하나로 만들었습니다. 여러분도 지금 이 순간 그 첫 번째 에이전트를 만들 수 있습니다."
