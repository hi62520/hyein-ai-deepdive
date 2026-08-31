---
date: 2026-09-01
category: AI네이티브회사
subject: Shopify / Tobi Lütke — 에이전틱 커머스 인프라 설계자
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱 대화창에 "AI 에이전트가 내 ERP 데이터를 찾아오는 엔드포인트가 있다면 어떻게 구조화할까?" 한 줄 질문 → 답 메모
---

# Shopify / Tobi Lütke — 플랫폼이 아닌 인프라가 됐을 때 해자가 생긴다

## 누구/무엇인가

Shopify는 2004년 캐나다 오타와에서 스노보드 용품 온라인 쇼핑몰 창업에 실패한 Tobi Lütke가 "직접 쓸 쇼핑몰 소프트웨어를 만들자"며 시작한 이커머스 플랫폼입니다. 현재 전 세계 200만 개 이상의 상점을 운영하며, Q2 2026 기준 GMV(총 거래액) $116B(약 155조 원)을 기록했습니다. 매출은 전년 동기 대비 34% 성장한 $3.58B으로 시장 컨센서스 $3.43B을 웃돌았고, 실적 발표 직후 주가가 18% 급등했습니다.

Lütke는 2025년 4월 전 직원에게 내부 메모를 통해 "AI 사용은 더 이상 선택이 아니다(AI use is no longer optional)"를 선언했고, 2026년에는 이를 사업 전략 전면에 배치해 "에이전틱 커머스(Agentic Commerce)" 개념을 실용화하고 있습니다. Shopify 사장 Harley Finkelstein은 Q2 실적발표에서 "Shopify는 아마 세계에서 가장 AI에 올인한 회사일 것(probably the most AI-pilled company in the world)"이라고 선언했습니다. 그 배후에는 Lütke의 집요한 방향 설정이 있습니다.

## 무엇이 특별한가

### 1. "AI가 못 하는 걸 증명해야 인력 요청 가능" — 내부 AI 의무화

Lütke의 2025년 메모는 단순한 독려가 아니라 인사·예산 기준을 바꿨습니다. "팀이 추가 인력이나 자원을 요청하기 전에, AI를 활용해서는 원하는 걸 얻을 수 없는 이유를 먼저 시연해야 한다(Before asking for more headcount and resources, teams must demonstrate why they cannot get what they want done using AI)." AI 역량은 성과 평가와 채용 기준에도 공식 반영됩니다. "정체는 느린 실패다(Stagnation is slow-motion failure)"라는 경고도 덧붙였습니다. 이것은 단순 생산성 향상이 아니라 조직 운영 모델 자체를 재설계한 것입니다.

### 2. 모든 상점을 에이전트 준비 상태로 기본값 변경

Winter 2026 에디션(150개 이상 업데이트)의 핵심 선언은 Lütke가 직접 한 한 줄입니다: "We're making every Shopify store agent-ready by default(우리는 모든 Shopify 상점을 에이전트 준비 상태로 기본 설정하고 있다)." 기술적으로는 ChatGPT, Google AI Mode, Microsoft Copilot, Perplexity가 상점의 제품 정보를 정확하게 읽고 거래를 완결할 수 있도록 데이터 구조와 API를 표준화한 것입니다. Google과 공동 개발한 Universal Commerce Protocol(UCP)에는 Amazon, Meta, Microsoft, Salesforce, Stripe가 참여했습니다.

### 3. 숫자가 검증해주는 전략 — AI 주문 13배, Sidekick 3400만 대화

Q1 2026: AI 채널 트래픽 전년 대비 8배 증가, AI 검색으로 발생한 주문 13배 증가. Q2 2026: AI 주문 3배 성장(속도는 줄었지만 규모가 커졌음), Sidekick AI 어시스턴트 대화 수 3,400만 건(일간 활성 상인 수 3.6배 증가, 일간 세션 4.8배 증가). 특히 상인들이 Sidekick을 이용해 Q2에만 맞춤 앱 36,000개를 생성했는데, 이는 Q1의 12,000개에서 3배 증가한 수치입니다. AI 채널에서 유입된 신규 구매자 주문 전환율은 다른 채널 대비 2배 높았고, AI 어트리뷰션 주문의 75%가 상위 100개 카테고리 이외에서 발생해 틈새 시장 발견 효과가 확인됐습니다.

### 4. 인프라 회사로의 재포지셔닝

Lütke가 2년 이상 공들인 핵심 포지셔닝 전환이 있습니다: Shopify는 이커머스 플랫폼이 아니라 에이전틱 커머스 인프라입니다. "Shopify is the easiest solution for merchants who want AI agents to find their storefronts, understand their products, and complete transactions." AI 에이전트가 ChatGPT 대화 속에서 실제 구매를 완결할 때, 그 뒤에서 결제·재고·배송을 처리하는 엔진이 Shopify입니다. 이커머스의 새 채널이 생길 때마다 Shopify가 기본 인프라가 되는 구조입니다. Q2 B2B GMV는 76% 성장해 기업 대상 판매에서도 이 전략이 먹히고 있음을 보여줬습니다.

### 5. Spring '26 "Everywhere Edition" — 채널 확장의 가속

Spring 2026 에디션("Everywhere Edition", 6월 17일 출시, 150개 이상 업데이트)은 '어디서나 판매 가능한 구조'를 완성했습니다. Shopify Catalog와 UCP가 제품 데이터를 구조화하여 ChatGPT, Copilot, Google AI Mode로 기본 송출합니다. 관리자 대시보드에는 각 AI 플랫폼별 에이전틱 스토어프런트 성과를 실시간으로 볼 수 있는 뷰가 추가됐습니다. Q2 국제 GMV 37% 성장도 이 전략의 결과물 중 하나입니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱 대화창에 "AI 에이전트가 내 ERP 데이터를 찾아오는 엔드포인트가 있다면 어떻게 구조화할까?" 한 줄 질문 → 답 메모. Shopify가 UCP로 한 것처럼, 와당탕 ERP가 외부 AI 에이전트에게 데이터를 노출할 구조를 머릿속에 한 번 그려보는 것이 목표입니다.

**이번 주 1-2시간 (mid)**: Shopify의 Sidekick처럼 비서앱 내에서 "자연어 명령 → ERP 액션" 파이프라인 1개 추가. 예: "이번 주 수업 예약 현황 알려줘" → 캘린더 API 조회 → 텍스트 요약 반환. 아래 스니펫을 참고하세요.

```python
# 비서앱 - 자연어 명령을 ERP 액션으로 변환하는 간단한 라우터
async def handle_natural_command(user_input: str, erp_client):
    # Claude에게 의도 파악 요청
    intent = await claude_classify(user_input, options=[
        "check_reservations", "check_revenue", "check_inventory", "general_chat"
    ])
    
    if intent == "check_reservations":
        data = await erp_client.get_weekly_reservations()
        return format_reservation_summary(data)
    elif intent == "check_revenue":
        data = await erp_client.get_weekly_revenue()
        return f"이번 주 매출: {data['total']:,}원 (예약 {data['count']}건)"
    else:
        return await claude_chat(user_input)
```

**이번 달 실험 (macro)**: ERP의 핵심 데이터(수업 예약, 매출, 고객 목록)를 외부 AI 에이전트가 안전하게 읽을 수 있는 엔드포인트 설계 → agent_key 인증 추가 → 실제로 Claude 에이전트가 "다음 주 수업 신청 현황 가져와" 명령으로 ERP를 호출하도록 연결. 측정 지표: 일주일 동안 몇 번 자연어 명령이 직접 ERP 액션으로 연결됐는지.

## 한국 솔로 운영자 맥락에서 주의

**플랫폼 전환 비용이 다름**: Shopify는 200만 상점을 기존 인프라 위에서 에이전트 준비 상태로 바꿨습니다. 대표님의 비서앱·ERP는 지금 설계하는 단계이므로, 오히려 처음부터 에이전트 친화적 API 구조를 설계할 수 있어 더 유리한 위치입니다. Shopify식 전환 스토리를 "교훈"으로 배우되, 대기업 레거시 전환 비용은 참고 불필요합니다.

**에이전틱 커머스는 B2C 전제가 강함**: Shopify의 사례는 ChatGPT가 소비자에게 제품을 추천하는 구조입니다. 느린호밀(베이커리), 와당탕연구소(강의·컨설팅)는 반복 단골 기반 사업이기 때문에 에이전트 발견보다는 에이전트 운영(기존 고객에게 알림, 예약 자동화, 루틴 처리)이 더 직접적인 가치입니다. 발견보다 실행에 먼저 투자하세요.

## 더 깊이 보려면

- [Shopify Winter 2026 Edition - Agentic Storefronts](https://www.shopify.com/news/winter-26-edition-agentic-storefronts)
- [Shopify CEO AI Memo (April 2025) - CNBC 분석](https://www.cnbc.com/2025/04/07/shopify-ceo-prove-ai-cant-do-jobs-before-asking-for-more-headcount.html)
- [Shopify Q2 2026 Earnings - AI Commerce Drives 34% Revenue Growth](https://finance.yahoo.com/technology/ai/articles/shopify-q2-earnings-call-spotlights-140000798.html)
- [Shopify Agentic Commerce 2026 Guide](https://www.aitrillion.com/blog/agentic-commerce-shopify-guide)
- [Applying Tobi Lütke AI Agents Question to Store Ops](https://www.get-ryze.ai/blog/applying-tobi-lutke-ai-agents-on-the-team-question-to-shopify-store-ops)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "AI 써야 한다"는 말은 들었지만, 어떻게 써야 할지 모르면 아무것도 바뀌지 않는다. Shopify는 그것을 "증명하지 못하면 인력 추가 없음"이라는 규칙으로 해결했다.
- **숫자**: Sidekick으로 만든 맞춤 앱 36,000개 — 1분기 12,000개에서 단 1분기 만에 3배. 이게 AI 도구 확산의 실제 속도다.
- **삽질**: Shopify도 처음에는 "AI 써라"고만 했다. 그런데 메모를 쓰고 인사 기준을 바꾸기 전까지 실제 사용률은 낮았다. 도구가 아니라 기준이 바뀌어야 행동이 바뀐다.
- **훅**: "당신 회사에서 AI가 못 하는 일을 먼저 증명해야 사람을 쓸 수 있다면, 당신은 어떤 업무부터 지켜낼 건가요?"
