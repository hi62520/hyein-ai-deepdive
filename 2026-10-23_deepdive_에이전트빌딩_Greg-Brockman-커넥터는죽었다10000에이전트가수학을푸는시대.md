---
date: 2026-10-23
category: 에이전트빌딩
subject: Greg Brockman — 커넥터는 죽었다, 10,000 에이전트가 수학을 푸는 시대
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱 ERP에서 외부 API 커넥터 대신 "에이전트 태스크" 항목 하나를 만들고, 사람이 클릭 대신 GPT/Claude에게 브라우저 열기 위임 실험을 30분 내 설계
---

# Greg Brockman — 커넥터는 죽었다, 10,000 에이전트가 수학을 푸는 시대

## 누구/무엇인가

Greg Brockman은 OpenAI의 공동창업자이자 President입니다. 2015년 Sam Altman, Elon Musk 등과 함께 OpenAI를 창립했으며, 초창기에는 CTO로서 GPT-1부터 GPT-4까지의 기술 기반을 닦았습니다. 2024년 8월, "더 많이 충전할 시간이 필요하다"는 이유로 장기 휴가를 선언해 AI업계를 놀라게 했지만, 같은 해 가을 조용히 복귀했습니다. 2026년 5월, OpenAI AGI 배포 CEO Fidji Simo가 의료 휴직에 들어가자 Brockman이 제품 전략 전체를 공식 인수하며 사실상 기술·제품·운영 삼각을 혼자 장악하게 됩니다. 현재 그의 OpenAI 지분 평가액은 약 300억 달러(약 41조 원)로, Musk 소송 과정에서 법원에 공개됐습니다. 조용한 스타일이지만, 공개적으로 발언할 때마다 에이전트 시대의 기술 방향을 가장 선명하게 정의하는 인물입니다.

## 무엇이 특별한가

**1. "커넥터를 만드는 시대는 끝났다"**

2026년 9월 GPT-6 Astra 출시 후 Brockman은 이런 말을 남겼습니다. *"We've been bottlenecked over this gigantic era by people writing connectors."* (우리는 이 거대한 시대 동안 커넥터를 만드는 사람들에 의해 병목이 걸려 있었다.) 에이전트가 브라우저를 열고, 스프레드시트를 읽고, 데스크탑 소프트웨어를 조작할 수 있게 되면, Zapier·Make·n8n 같은 "중간 연결 도구"가 필요 없어진다는 선언입니다. 와당탕 대표님이 ERP와 비서앱을 직접 짜는 이유가 바로 여기에 있습니다 — 커넥터 레이어가 사라지면, 인터페이스와 의도를 설계한 사람이 가장 강합니다.

**2. 10,000 에이전트가 88시간 만에 90년 수학 난제를 풀다**

2026년 9월, OpenAI는 내부 모델 10,000개 에이전트를 Navier-Stokes 방정식 문제에 투입했습니다. 결과: 88시간, 약 2,700만 에이전트 메시지, 1,300억 토큰 소비, 그리고 Lean 언어로 공식 검증된 증명. 수학자들 사이에서 "풀려는 버전이 Clay 밀레니엄 상금 기준 버전이 아니다"는 논쟁이 있었지만, 핵심은 이것입니다: **대규모 병렬 에이전트 시스템이 단일 천재의 수십 년 연구를 88시간으로 압축했다.** Brockman은 이 결과를 들어 *"it's not unreasonable to feel that we are now in the AGI era"* (우리가 이제 AGI 시대에 있다고 느끼는 것이 터무니없지 않다)라고 말했습니다.

**3. ChatGPT + Codex + API = 에이전트 슈퍼앱 통합**

Brockman이 제품 전략을 가져온 뒤 가장 먼저 한 일은 내부 "사이드 퀘스트" 종료입니다. Sora(동영상 생성기)와 OpenAI for Science 프로젝트를 중단하고, ChatGPT·Codex·API를 Atlas 브라우저와 함께 하나의 통합 플랫폼으로 수렴하겠다는 방향을 선포했습니다. Codex CEO Thibault Sottiaux가 이 통합 팀을 이끌며, 실질적으로는 "대화 → 코딩 → 배포 → 운영"이 한 흐름 안에서 완결되는 에이전트 슈퍼앱을 목표로 합니다. 이것이 완성되면, 솔로 운영자 입장에서는 "도구를 옮겨다니는 마찰"이 제거되는 것입니다.

**4. 생산 엔지니어의 25%를 보안에 투입**

Brockman은 a16z 팟캐스트에서 이런 수치를 공개했습니다: OpenAI는 자사 생산 엔지니어의 약 25%를 자사 시스템 방어에 재배치했고, 자체 모델을 자체 시스템에 공격자로 돌렸다고 했습니다. "발견이 포화될 때까지" 계속했다는 표현을 썼는데, 이는 에이전트가 외부 도구를 탈취할 수 있는 시대에 보안이 기능이 아닌 기초 인프라가 됐다는 신호입니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱 ERP에서 외부 API 커넥터 대신 "에이전트 태스크" 항목 하나를 만들고, 사람이 클릭 대신 GPT/Claude에게 브라우저 열기 위임 실험을 30분 내 설계. 예: "배송 현황 확인" 버튼 → 에이전트가 택배사 사이트를 직접 열고 결과를 돌려주는 플로우 스케치.

**이번 주 1-2시간 (mid)**: ChatGPT Codex나 Claude Code에서 "커넥터 없는 작업" 1가지를 선정해 실제 에이전트 세션으로 테스트. 예: 구글 시트 직접 접근, 카카오 채널 메시지 확인 등. 성공/실패 여부 + 소요 토큰을 기록해 커넥터 방식 대비 효율을 비교.

```python
# 커넥터 vs 에이전트 비용 비교 스케치
connector_setup_hours = 3  # Make/Zapier 설정 시간
agent_setup_hours = 0.5    # 프롬프트 작성 시간
connector_monthly_usd = 29  # Make Pro 기준
agent_tokens_per_task = 2000  # 토큰 추정
agent_tasks_per_month = 100
agent_cost_usd = (agent_tokens_per_task * agent_tasks_per_month * 3) / 1_000_000  # $3/1M tokens

print(f"커넥터 방식: 설정 {connector_setup_hours}h + 월 ${connector_monthly_usd}")
print(f"에이전트 방식: 설정 {agent_setup_hours}h + 월 ${agent_cost_usd:.2f}")
```

**이번 달 실험 (macro)**: 와당탕 ERP 내 "커넥터로 구현한 기능" 목록을 작성하고, 에이전트로 대체 가능한지 항목별로 표시. 3개 이상이면 통합 에이전트 레이어 설계를 시작. 측정 지표: 대체 성공률, 월 비용 절감, 설정 시간 감소.

## 한국 솔로 운영자 맥락에서 주의

**Navier-Stokes 규모는 직접 참고가 안 됩니다.** 10,000 에이전트, 130억 토큰 — 이건 OpenAI가 내부 인프라와 비용을 사실상 무제한으로 쓸 수 있기 때문에 가능한 규모입니다. 와당탕/느린호밀 수준에서 실험할 때는 "에이전트 개수"보다 "작업 하나를 올바르게 위임하는 설계"에 집중해야 합니다. 큰 수가 인상적으로 보여도, 솔로 운영자에게 실제로 쓸 수 있는 단위는 2-3개 병렬 에이전트입니다.

**"커넥터 시대 종료" 선언을 너무 빨리 받아들이면 위험합니다.** Computer-use 에이전트는 아직 속도·안정성·신뢰성 면에서 제한이 있습니다. GPT-6 Astra가 브라우저를 잘 조작한다고 해서 당장 내일 Make/n8n을 다 끊으면 운영이 끊깁니다. Brockman의 방향은 맞지만, 지금은 "커넥터와 에이전트 병렬 실험" 시기입니다.

## 더 깊이 보려면

- [OpenAI co-founder Greg Brockman takes charge of product strategy (TechCrunch)](https://techcrunch.com/2026/05/16/openai-co-founder-greg-brockman-reportedly-takes-charge-of-product-strategy/)
- [OpenAI Launches GPT-6 Astra — 'AGI Era' Has Arrived (TechRepublic)](https://www.techrepublic.com/article/news-openai-gpt-6-astra-agi-era-2026/)
- [OpenAI 10,000 AI Agents Solved Navier-Stokes in 88 Hours (RuntimeWire)](https://runtimewire.com/article/openai-10000-ai-agents-navier-stokes-proof)
- [Greg Brockman: OpenAI put 25% of engineers onto defending its own systems (GoldenAge)](https://www.joingoldenage.com/p/greg-brockman-openai-put-25-of-its)
- [Greg Brockman Consolidates OpenAI Product Teams (The Decoder)](https://the-decoder.com/greg-brockman-consolidates-openais-product-teams-to-build-an-agentic-future/)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "Zapier 연동 설정하는 데 하루 쓰고 나서, 에이전트가 그냥 브라우저 열면 된다는 걸 알았다." — 커넥터를 배우는 것 자체가 곧 레거시 스킬이 될 수 있다는 공포.
- **숫자**: 10,000 에이전트 × 88시간 = 880,000 에이전트-시간. 한 사람이 하루 8시간 일한다면 110,000일, 약 300년치 작업. 그게 88시간 안에 완료됐다.
- **삽질**: OpenAI는 Sora에 막대한 리소스를 쏟고 나서 중단했다. "사이드 퀘스트를 끊는 결단"이 속도를 만든다 — 와당탕에서도 '안 쓰는 기능'을 지금 당장 리스트업할 것.
- **훅**: "당신이 지금 설정하고 있는 그 커넥터, 1년 후엔 에이전트가 대신 합니다. 그러면 당신이 설계해야 하는 건 커넥터가 아니라 의도입니다."
