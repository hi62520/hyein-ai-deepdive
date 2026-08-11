---
date: 2026-08-12
category: 팟캐스트뉴스레터
subject: Ben Thompson (Stratechery) — 에이전트 추론 전환, SaaSmageddon, 데이터센터 거부권
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱·ERP에서 "사람이 중간에 확인하는" 단계 하나를 Obsidian에 메모한다 — Thompson의 'agentic inference' 프레임으로 대체 가능한지 검토
---

# Ben Thompson (Stratechery) — 에이전트가 SaaS를 먹고, 데이터센터 거부권이 AI를 멈춘다

## 누구/무엇인가

Ben Thompson은 대만 타이베이 거주 독립 테크 애널리스트입니다. 2013년 시작한 유료 뉴스레터 **Stratechery**는 현재 구독자 수가 수십만 명을 넘어서며, 구독료 월 $15 / 연 $150 단일 수익 구조를 10년 이상 유지하는 솔로 미디어의 교과서입니다. 광고 없음. 직원은 본인과 팟캐스트 공동진행자 Andrew Parrish 둘뿐입니다. 뉴스레터 "Stratechery Plus"와 팟캐스트 "Sharp Tech"를 운영하며, Stripe 존 콜리슨 인터뷰(Cheeky Pint)·MoffettNathanson 컨퍼런스 등 외부 행사에서도 자신의 분석을 업데이트합니다.

Thompson의 핵심 이론은 **집계이론(Aggregation Theory)** — "인터넷은 공급자를 상품화하고, 사용자를 직접 통제하는 자가 독점적 가치를 갖는다"는 프레임입니다. 2026년, 그는 이 이론이 AI 에이전트 시대에 어떻게 재편되는지를 집중 추적 중입니다. 5월 딥다이브(2026-05-20)에서 집계이론의 종언을 다뤘다면, 이번에는 2026년 상반기~8월까지 Thompson이 정리한 **신(新) 프레임워크 4개**를 해부합니다.

## 무엇이 특별한가

### 1. "추론 전환(The Inference Shift)" — 속도가 의미 없어지는 세계

2026년 5월 발표한 "The Inference Shift"는 인퍼런스를 두 종류로 분리합니다.

- **Answer Inference (응답 추론)**: 사람이 결과를 기다림. 속도 = UX. 빠른 칩이 경쟁력.
- **Agentic Inference (에이전트 추론)**: 사람이 루프 밖. 속도는 무의미. 처리 **총량**과 **비용당 효율**이 전부.

> "Agentic inference is going to be different than the inference we use today, and it will change compute infrastructure because **speed won't matter when humans aren't involved.**"

기술적으로 인퍼런스는 ① Prefill(컴퓨트 바운드) ② 어텐션 디코딩(대역폭 바운드, 직렬) ③ 피드포워드 디코딩(대역폭 바운드, 직렬) 세 컴포넌트로 나뉩니다. 에이전트 추론은 CPU 기반 오케스트레이션 컴퓨팅이 별도로 필요해, Nvidia GPU 중심 아키텍처와는 전혀 다른 인프라 선택을 요구합니다. Thompson은 이 전환이 "점점 더 이기종(heterogeneous) 컴퓨팅 구조"로 이어질 것이라고 씁니다.

와당탕 ERP에서 이 구분은 즉각 적용 가능합니다. 비서앱에서 대표님이 직접 승인하는 단계(응답 추론 영역)와, 에이전트가 밤새 자동 처리해도 되는 단계(에이전트 추론 영역)를 구분하면 인프라 비용을 크게 줄일 수 있습니다.

### 2. "거품 너머의 에이전트(Agents Over Bubbles)" — 입장을 공식 철회한 이유

2026년 3월, Thompson은 공개적으로 "AI는 버블이 아니다"로 입장을 바꿨습니다. 근거는 **LLM 3대 변곡점**:

1. **ChatGPT (2022.11)** — 토큰 예측이 실용적임을 증명
2. **o1 계열** — 추론 단계: 토큰을 더 쓸수록 답이 좋아진다
3. **Claude Code + Opus 4.5** — 최초의 실사용 가능 에이전트: 도구 사용·검증·하네스 조합으로 실제 작업을 완수

> "Every single hyperscaler says that demand for compute exceeds supply, and every single hyperscaler is announcing capex plans that blow away expectations despite stock market skepticism."

수치: 아마존·구글·메타의 2026년 합산 AI CapEx는 **7,000억 달러를 초과** — "미 국방부 연간 예산의 약 2/3"에 해당합니다. Thompson은 이 규모를 버블로 보는 시장의 시선이 틀렸다고 주장합니다. 에이전트는 단일 쿼리가 아니라 **연쇄 추론 호출** + **오케스트레이션 컴퓨팅**을 동시에 소비하기 때문입니다. 수요 창출의 구조 자체가 달라졌습니다.

역사적 유비: Thompson이 8월 11일 "Nvidia's Risky Business"에서 인용한 수치 — 1870년대 미국 철도 채권에 연간 투자된 $5억은 오늘날 약 **$6,000억**에 해당합니다. AI 인프라 투자와 정확히 같은 규모입니다. 그는 "철도 버블은 결국 실물 인프라를 남겼다"는 낙관적 해석과 동시에, Nvidia가 유기적 수요에서 **제조된 수요(금융 메커니즘 활용)**로 전환하고 있다는 위험 신호를 함께 짚습니다.

### 3. "SaaSmageddon" — 누가 살고 누가 죽는가

2026년 2월 "SaaSmageddon and the Super Bowl"과 "Microsoft and Software Survival"에서 Thompson이 제시한 SaaS 재편 지도입니다.

> "The real risk for software companies is that while they can write infinite software thanks to AI, so can every other software company, which will completely upend the relatively neat and infinitely siloed SaaS ecosystem that has been Silicon Valley's bread-and-butter for the last decade."

그러나 동시에 반론도 냅니다:

> "The public markets are wrong to think SaaS is 'canceled.'"

취소가 아니라 **재편**입니다. 구체적으로:

- **앱 내장 에이전트**: 각 SaaS가 자체 에이전트를 포함하되, 앱 경계 내에 갇힌다
- **수평 에이전트 플레이어**: Microsoft처럼 조직 전체를 아우르는 시도 ("Work IQ", MS365 CoPilot — 현재 유료 고객 **1,500만 명**, 전체 MS365 고객 기반의 극히 일부)
- **모델 메이커 직접 운영**: 모델 역량을 가장 잘 활용하는 주체는 결국 모델을 만드는 회사 자신

Microsoft의 전략을 Thompson은 이렇게 요약합니다:

> "The software that wins will use AI to usurp other software."

그리고 기업 고객 입장에서 냉혹한 현실:

> "Businesses may not give up on software, but they don't necessarily want to buy more — if anything, they need to cut their spending so they have more money for their **own tokens**."

즉, 기업들이 SaaS 구독료를 줄이는 이유는 소프트웨어가 필요 없어서가 아니라, 그 돈을 **직접 AI 토큰 소비**에 써야 하기 때문입니다. 솔로 운영자에게 이 구조 변화는 직접적입니다 — 현재 지출하는 SaaS 구독료 일부를 AI 에이전트 비용으로 대체하는 경로가 열리고 있습니다.

Microsoft는 이 경쟁에서 유일하게 "실질적 현금흐름"을 가진 하이퍼스케일러임을 Thompson은 강조합니다 — 지난 분기 자유현금흐름 **$196억 달러**.

### 4. "데이터센터 거부권(The Data Center Veto)" — AI의 물리적 한계

2026년 5월 발표한 가장 독특한 프레임워크입니다.

> "AI depends on data centers in the physical world… building data centers requires permission."

Thompson의 핵심 주장: 세계화가 진행될 때 노동자들은 디지털 영역에서 저항할 수단이 없었습니다. 그러나 AI는 **물리적 인프라**가 필요하고, 그 인프라는 지역사회의 토지·전력·수자원을 소비합니다. 일반 시민은 데이터센터 건설에 대한 **거부권**을 갖습니다.

오해와 역정보, 지역 반대 운동은 "증상"이 아니라 "원인"입니다. AI의 혜택은 디지털 세계에서 느껴지지만, 비용(토지, 소음, 열, 물)은 물리적 세계에서 지역 주민이 부담합니다. 이 비대칭이 AI 확산의 가장 큰 변수 중 하나가 될 것이라는 예측입니다.

Nvidia는 이를 우회하기 위해 Apollo·BlackRock·Blackstone·Brookfield·Goldman Sachs·KKR 등 금융기관과 파트너십으로 **5,000억 달러+** 규모의 제3자 자본을 AI 인프라에 투입하는 구조를 만들고 있습니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱·ERP에서 "사람이 중간에 확인하는" 단계 하나를 Obsidian에 메모한다 — Thompson의 'agentic inference' 프레임으로 대체 가능한지 검토. (예: "주문 확인 메시지 발송 전 대표님 승인" → 에이전트가 자동 처리 가능한가? 가능하다면 이미 'agentic inference 영역')

**이번 주 1-2시간 (mid)**: Thompson의 SaaSmageddon 3레이어 지도를 와당탕 ERP에 적용한다. 현재 사용 중인 SaaS 구독 목록을 뽑고, 각각을 ① 에이전트로 대체 가능 ② 내장 에이전트로 유지 ③ 수평 에이전트(Claude Code)로 흡수 가능 중 하나로 분류.

```python
# SaaSmageddon 지도 적용 예시
saas_audit = [
    {"name": "구글 워크스페이스", "monthly_cost": 12000, "status": "유지"},
    {"name": "노션 팀플랜", "monthly_cost": 16000, "status": "Obsidian+Claude로 대체 가능"},
    {"name": "재고관리 SaaS", "monthly_cost": 50000, "status": "ERP 내장 에이전트로 흡수 가능"},
    {"name": "고객관리 CRM", "monthly_cost": 35000, "status": "비서앱 에이전트로 흡수 가능"},
]
replaceable = [s for s in saas_audit if "대체" in s["status"] or "흡수" in s["status"]]
savings = sum(s["monthly_cost"] for s in replaceable)
print(f"에이전트 대체로 월 {savings:,}원 절감 가능")
```

**이번 달 실험 (macro)**: "agentic inference 비율 로그" 운영. 비서앱에서 한 달간 에이전트 자동처리 건수 vs 대표님 개입 건수를 기록. 목표: 자동처리 70% / 개입 30%. 이 수치가 Thompson의 "추론 전환" 실질 진행률이며, SaaS 구독 절감의 선행 지표가 됩니다.

## 한국 솔로 운영자 맥락에서 주의

**"네트워크효과 기업이 AI 최후 승자"라는 메시지는 솔로 운영자에게 잘못 읽힐 수 있습니다.** Spotify·Google처럼 수억 명 데이터를 가진 집계자 논리를 1인 사업에 그대로 적용하면 "나는 데이터가 없으니 못 한다"는 패배주의로 이어집니다. 실제로 솔로 운영자의 강점은 반대입니다 — 수백 명 고객을 깊이 알고, 한 명씩 맞춤화하는 에이전트가 대기업보다 훨씬 빠르게 구현됩니다.

**"SaaSmageddon = SaaS 구독 무조건 해지"로 읽으면 안 됩니다.** Thompson의 주장은 "취소가 아니라 재편"입니다. 에이전트로 대체 가능한 것과 협업 도구처럼 대체 불가능한 것을 구분하지 않고 일괄 해지하면 운영 공백이 생깁니다.

## 더 깊이 보려면

- [Stratechery — Agents Over Bubbles (2026.03)](https://stratechery.com/2026/agents-over-bubbles/)
- [Stratechery — The Inference Shift (2026.05)](https://stratechery.com/2026/the-inference-shift/)
- [Stratechery — Aggregators and AI (2026.02)](https://stratechery.com/2026/aggregators-and-ai/)
- [Stratechery — Microsoft and Software Survival (2026.02)](https://stratechery.com/2026/microsoft-and-software-survival/)
- [Stratechery — The Data Center Veto (2026.05)](https://stratechery.com/2026/the-data-center-veto/)
- [Stratechery — Nvidia's Risky Business (2026.08.11)](https://stratechery.com/2026/nvidias-risky-business/)
- [Sharp Tech Podcast — MoffettNathanson 인터뷰 (Spotify)](https://open.spotify.com/episode/1ZNlgTiQIg3OwsqePHaCrx)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "SaaS 구독료는 매달 나가는데 직원처럼 일하지 않는다. 에이전트는 다르다 — 밤새 처리하고, 속도를 따지지 않으며, 실수하면 로그가 남는다. Thompson이 말한 '아젠틱 인퍼런스'가 바로 이것이다."
- **숫자**: 아마존·구글·메타 2026년 합산 AI CapEx **7,000억 달러 초과** — 미 국방부 연간 예산 2/3. 이것이 버블이 아닌 이유는 에이전트가 소비하는 컴퓨팅 총량이 인간 주도 인퍼런스보다 구조적으로 훨씬 크기 때문이다.
- **삽질**: 세계 최고 테크 애널리스트 Thompson 본인도 한때 AI를 "버블 가능성 있음"으로 분류했다가 2026년 3월 공식 철회. "Claude Code로 에이전트가 실제 일을 끝낼 수 있게 됐을 때" 입장을 바꿨다고 밝혔다.
- **훅**: "당신이 지금 쓰는 SaaS 구독료 절반은 3년 안에 에이전트에게 자리를 뺏깁니다. 문제는 그 에이전트를 당신이 쥐느냐, 대형 플랫폼이 쥐느냐입니다. Thompson은 기업에게 이것을 경고했지만, 솔로 운영자에게는 오히려 기회입니다."
