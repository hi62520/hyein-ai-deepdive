---
date: 2026-09-27
category: 주간종합
subject: 집계이론 역독 — Salesforce는 UI를 버리는데 왜 와당탕은 UI를 직접 짜야 하는가
tags: [AI탐구, deepdive]
starred: false
micro_action: ERP나 비서앱에 '다른 서비스는 절대 가질 수 없는' 데이터 필드 1개 추가하기 (예: 와당탕 고유 원가 계산식, 느린호밀 빵 발효 타임스탬프)
---

# 집계이론 역독 — Salesforce는 UI를 버리는데, 왜 와당탕은 UI를 직접 짜야 하는가

## 이번 주 재조명 선정 이유

지난 수요일(9월 23일) Ben Thompson의 집계이론 2026 업데이트를 다뤘습니다. 그 글의 핵심은 "에이전트가 새로운 집계자가 된다 → 기존 SaaS의 UI 해자가 사라진다 → 비서앱은 맥락 데이터를 소유해야 한다"는 하향식 분석이었습니다. 그런데 읽고 나서 대표님이 실제로 맞닥뜨린 질문은 이것일 겁니다:

**"Salesforce가 UI를 버린다면, 나는 왜 지금 Claude Code로 ERP UI를 새벽까지 짜고 있어야 하는가?"**

이 질문이 사실 집계이론 전체를 한 바퀴 더 돌 때 나오는 진짜 통찰입니다. 오늘은 그 역방향 독법을 정리합니다.

---

## Salesforce가 UI를 버리는 이유 — 이미 데이터 모트가 있기 때문

Thompson이 9월 ["Salesforce AI Force, Agents as UI, The Race to Headless"](https://stratechery.com/2026/salesforce-ai-force-agents-as-ui-the-race-to-headless/)에서 쓴 문장이 있습니다:

> *"Salesforce abandoning UI as a moat is actually a very smart move — because the UI moat is disappearing for everyone."*

왜 Salesforce가 이걸 감수할 수 있을까요? 정답은 단순합니다. Salesforce에는 **20년 치 CRM 데이터**가 있습니다. 수십만 개 기업의 영업 파이프라인, 고객 접촉 이력, 계약 기록이 Salesforce 데이터베이스에 잠겨 있습니다. 에이전트가 UI를 삼켜도, 에이전트가 참조해야 할 데이터는 여전히 Salesforce에 있습니다. UI를 포기해도 데이터 종속성이 남아 있기 때문에 `headless`(UI 없는 백엔드) 전략이 통하는 겁니다.

집계이론의 핵심 공식:

```
집계 권력 = 고객 관계 소유 × 공급자 상품화
```

Salesforce는 이미 "고객 관계 소유" 단계를 완성했습니다. 그래서 UI라는 집계 수단을 에이전트에게 양도해도 됩니다.

---

## 와당탕의 현재 좌표 — 데이터 모트가 아직 없다

와당탕연구소와 느린호밀은 지금 어디에 있을까요?

- 아직 자체 ERP가 완성되지 않음
- 비서앱이 아직 운영 데이터를 충분히 축적하지 못함
- 고객 관계 데이터가 카카오·인스타·외부 POS 등에 분산되어 있음

집계이론 공식에 대입하면:

```
와당탕 집계 권력 = 고객 관계 소유(△) × 공급자 상품화(0)
```

데이터 모트가 없는 상태에서 헤드리스 전략을 쓰면, 에이전트에게 줄 데이터 자체가 없습니다. 에이전트가 질문을 해도 당기할 데이터베이스가 없는 셈입니다. Salesforce와 동일한 전략이 작동하지 않는 이유입니다.

---

## 무엇이 특별한가 — 동일 이론에서 반대 결론이 나오는 이유

### 1. "UI를 직접 짜는 행위 = 데이터 모트를 쌓는 행위"

Thompson은 ["Agents Over Bubbles"](https://stratechery.com/2026/agents-over-bubbles/)에서 아이러니한 고백을 합니다. 에이전트 시대를 분석하던 그가 직접 "에이전트 코딩을 해보았더니 너무 재밌어서 새로운 소프트웨어 프로젝트를 여러 개 시작했다"고 씁니다:

> *"I dove headfirst into agentic coding for myself and have been so taken by the possibilities of making software for myself that I started multiple new projects over the past few months."*

집계이론을 쓰는 사람이 왜 직접 소프트웨어를 만들까요? 그가 쌓는 것은 UI가 아니라 **그만의 데이터 구조**입니다. 분석 도구, 구독자 행동 데이터, 발행 이력 — 이것들이 그가 Substack이나 Ghost에 의존하지 않는 이유입니다. 남의 플랫폼을 쓰면 그 데이터는 플랫폼 것이 됩니다.

와당탕이 Claude Code로 ERP를 직접 짜는 것은 정확히 같은 논리입니다. **UI를 만드는 것 = 그 UI를 통해 흐르는 데이터를 자신이 소유하는 것.**

### 2. "누가 구경꾼이고 누가 설계자인가"

Thompson의 집계이론에서 집계자가 공급자를 상품화할 수 있는 이유는, 집계자가 **무엇을 사용자에게 노출시킬지**를 결정하기 때문입니다. Google이 검색 결과를 설계하고, Amazon이 상품 노출 알고리즘을 설계합니다.

에이전트 시대의 핵심 질문: **에이전트가 와당탕 비즈니스를 이해할 때, 어떤 데이터를 보게 할 것인가?**

이 설계권을 가진 사람이 새로운 집계자입니다. 그 데이터가 Notion이나 외부 SaaS 안에 있으면, 그 설계권이 Notion에게 있는 겁니다. 데이터가 직접 만든 ERP에 있으면, 설계권이 대표님에게 있습니다.

```python
# 외부 SaaS에 데이터가 있을 때
agent.query("오늘 느린호밀 매출 요약해줘")
→ Notion API 경유 → Notion 데이터 스키마 의존 → Notion이 설계자

# 직접 만든 ERP에 데이터가 있을 때  
agent.query("오늘 느린호밀 매출 요약해줘")
→ 자체 ERP API 경유 → 와당탕 고유 스키마 → 대표님이 설계자
```

### 3. "Salesforce의 시간축 vs. 와당탕의 시간축"

Thompson의 분석에서 종종 놓치는 것이 있습니다. Salesforce가 지금 UI를 버리는 것은 **1999년부터 2025년까지 26년간 UI를 가져갔기 때문**입니다. UI가 없어도 될 만큼 데이터가 충분히 쌓인 것입니다.

와당탕은 2026년 지금, Salesforce의 1999년 위치에 있습니다. 이 시점에 UI를 건너뛰면, 26년 치의 데이터 없이 2025년의 Salesforce를 흉내 내는 꼴이 됩니다. **Salesforce의 지금 전략이 아니라 Salesforce의 1999년 전략을 참고해야 하는 시점**입니다.

Thompson이 말한 "헤드리스 레이스"는 이미 데이터 모트를 가진 플레이어 간의 경쟁입니다. 모트를 아직 파지 않은 플레이어는 먼저 모트를 파야 합니다.

### 4. "공급자 상품화를 역이용하라 — SaaS가 공급자가 되는 순간"

집계이론의 아이러니는, **소규모 솔로 운영자도 집계자가 될 수 있다**는 점입니다. 대상이 사용자가 아니라 도구와 서비스가 되면 됩니다.

와당탕이 직접 ERP를 만들고, 그 ERP가 카카오 메시지 API, 배달 플랫폼 데이터, 재고 POS를 연결하면:

```
와당탕 ERP = 소집계자
카카오 API, 배달플랫폼, POS = 공급자(상품화 대상)
```

이 구조에서 외부 API는 교체 가능한 부품이 되고, 와당탕 ERP는 유일한 판단 레이어가 됩니다. Thompson의 표현을 빌리면:

> *"Power flows to the player that owns the customer relationship and commoditizes everyone else."*

여기서 "고객 관계"를 "비즈니스 데이터 관계"로 치환하면, 이것이 정확히 와당탕이 지금 구축하고 있는 것입니다.

---

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: ERP나 비서앱에 '다른 서비스는 절대 가질 수 없는' 데이터 필드 1개를 추가하세요. 예:
- 와당탕연구소: 강의별 수강생 재구매 간격 (느린호밀 재방문율과 교차 분석 가능)
- 느린호밀: 빵 종류별 발효 시작 시간 타임스탬프 (폐기율 예측 모델 원천 데이터)

이 필드는 Notion이나 외부 SaaS에 절대 없습니다. 이 필드가 데이터 모트의 첫 번째 벽돌입니다.

**이번 주 1-2시간 (mid)**: 현재 운영 중인 외부 도구(카카오, 인스타 DM, 배달앱, POS)에서 나오는 데이터 중, ERP가 직접 수집해야 할 항목 리스트를 만드세요. 각 항목 옆에 "지금 이 데이터의 소유자가 누구인가"를 적으세요. 소유자가 외부 플랫폼인 것이 데이터 모트 공백입니다.

```python
# ERP 고유 데이터 캡처 예시
def record_bread_batch(bread_type: str, fermentation_start: datetime, 
                       bake_start: datetime, units_made: int):
    """
    느린호밀 전용 — 발효 시작·굽기 시작·생산량 레코드.
    이 데이터는 어떤 SaaS도 수집하지 않음. 에이전트가 폐기율 예측할 때 
    유일한 참조 데이터가 된다.
    """
    db.insert("bread_batches", {
        "bread_type": bread_type,
        "fermentation_start": fermentation_start,
        "bake_start": bake_start,
        "fermentation_hours": (bake_start - fermentation_start).hours,
        "units_made": units_made,
        "date": datetime.today()
    })
```

**이번 달 실험 (macro)**: "데이터 소유권 지도" 작성. 와당탕·느린호밀의 모든 운영 데이터를 종이에 매핑하고, 각 데이터의 현재 소유자를 표시하세요. 30일 후 ERP로 이전 완료된 데이터 비율을 측정 지표로 삼습니다. 이것이 집계이론 관점의 실질적 진척도입니다.

---

## 한국 솔로 운영자 맥락에서 주의

**"Salesforce 흉내" 함정**: Thompson의 헤드리스 논의를 읽고 "나도 API 먼저 만들고 UI는 나중에"라는 결론을 내리는 것은 위험합니다. 데이터 모트 없는 API 우선 전략은 작동하지 않습니다. UI를 통해 데이터를 먼저 쌓고, 그 다음에 헤드리스를 논의하세요.

**"데이터 모트 = 양" 착각**: 많은 데이터가 아니라 **독점적 데이터**가 해자입니다. 1년 치 느린호밀 발효 타임스탬프 데이터는, 수백만 건의 일반 식품 판매 데이터보다 '느린호밀 에이전트'에게 훨씬 더 가치 있습니다. 독점성을 먼저 설계하세요.

---

## 더 깊이 보려면

- [Aggregators and AI – Stratechery](https://stratechery.com/2026/aggregators-and-ai/)
- [Salesforce AI Force, Agents as UI, The Race to Headless – Stratechery](https://stratechery.com/2026/salesforce-ai-force-agents-as-ui-the-race-to-headless/)
- [Agents Over Bubbles – Stratechery](https://stratechery.com/2026/agents-over-bubbles/)
- [원본 딥다이브 (9/23) — 에이전트가 UI를 삼킬 때 해자는 어디에 남는가](./2026-09-23_deepdive_팟캐스트뉴스레터_Ben-Thompson-Stratechery-집계이론2026-에이전트가UI를먹을때.md)

---

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "Thompson 읽고 '에이전트 시대엔 UI 필요 없겠다'고 결론 내린 솔로 창업자들, 이미 데이터 모트가 없는 상태에서 UI까지 버리면 에이전트에게 줄 게 아무것도 없다."
- **숫자**: Salesforce — 26년 치 CRM 데이터로 UI를 버릴 수 있다. 와당탕 — 아직 데이터 모트 Day 1. 이 숫자 차이가 전략 차이를 만든다.
- **삽질**: Thompson 본인도 에이전트 시대 분석을 쓰면서 직접 소프트웨어를 만들기 시작했다. "이론을 쓰는 사람도 데이터 모트를 직접 짠다."
- **훅**: "Salesforce가 UI를 버린다는 뉴스를 보고 '나도 버려야지'라고 생각했다면, 당신은 지금 Salesforce의 1999년이 아닌 2026년을 흉내 내고 있는 겁니다."
