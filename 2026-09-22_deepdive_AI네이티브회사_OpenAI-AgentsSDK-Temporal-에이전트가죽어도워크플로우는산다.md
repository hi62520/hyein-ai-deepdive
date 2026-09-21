---
date: 2026-09-22
category: AI네이티브회사
subject: OpenAI Agents SDK × Temporal — 에이전트가 죽어도 워크플로우는 산다
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱 에이전트 중 가장 오래 실행되는 흐름(예: 주간보고 생성)을 찾아, "이 흐름이 중간에 꺼지면 어떻게 되는가?" 한 줄로 기록해두기
---

# OpenAI Agents SDK × Temporal — 에이전트가 죽어도 워크플로우는 산다

## 누구/무엇인가

OpenAI Agents SDK는 2026년 3월 프로덕션 표준으로 GA(정식 출시)된 에이전트 빌딩 프레임워크입니다. 그 이전까지 실험적 교육 도구였던 Swarm 프레임워크를 대체하며, 단 5개의 핵심 프리미티브(Agent, Runner, Tools, Handoffs, Guardrails, Sessions)만으로 프로덕션급 멀티에이전트 시스템을 구축할 수 있도록 설계됐습니다. 같은 달, 워크플로우 오케스트레이션 플랫폼 Temporal이 OpenAI Agents SDK와의 통합을 동시에 GA로 발표하면서, "에이전트가 죽어도 워크플로우는 멈추지 않는" 내구성 실행(durable execution) 패러다임이 처음으로 프로덕션 수준에서 구현됐습니다. Temporal은 Netflix, Stripe, Coinbase 등 수천 개 기업에서 미션 크리티컬 워크플로우를 운영하는 인프라로, 이 통합은 AI 에이전트를 "실험"이 아닌 "운영 인프라"로 바꾸는 분기점이 됐습니다. 대표님이 Claude Code로 구축 중인 비서앱·ERP와 직결되는 패턴이기도 합니다.

## 무엇이 특별한가

**1. 5개 프리미티브만으로 멀티에이전트 전체를 커버한다**

OpenAI Agents SDK의 설계 철학은 "최소한의 추상화"입니다. Agent(지시·모델·도구·핸드오프 정의), Runner(에이전트 루프 실행), Tools(함수·웹검색·코드실행), Handoffs(다른 에이전트로 제어 이전), Guardrails(입출력 검증), Sessions(대화 상태 영속) — 이 6가지로 LangGraph·CrewAI 수준의 복잡한 멀티에이전트 시스템을 구현할 수 있습니다. OpenAI 공식 문서는 "추상화는 배울수록 약이 아니라 독이 된다(abstractions learned the hard way become poison)"고 명시하며, 최소 프리미티브 설계를 의도적으로 고집했다고 밝혔습니다.

**2. Manager 패턴 vs Handoff 패턴 — 선택이 아키텍처를 결정한다**

두 가지 핵심 오케스트레이션 패턴이 있습니다. **Manager 패턴**: 중앙 오케스트레이터가 전문 서브에이전트를 "도구처럼" 호출하며 대화 제어권을 유지합니다. 조율이 필요하고 출력 형식이 통일돼야 할 때 적합합니다. **Handoff 패턴**: 에이전트가 다른 에이전트에게 대화 전체를 넘기며, 인수받은 에이전트가 전체 컨텍스트를 보고 이어서 실행합니다. 고객 상담에서 1차 트리아지 에이전트 → 결제 전문 에이전트 → 환불 승인 에이전트로 넘어가는 흐름이 대표적입니다. 선택 기준은 단순합니다: 결과를 한 곳에서 합쳐야 하면 Manager, 바통을 완전히 넘겨도 되면 Handoff.

**3. Temporal 통합 = 에이전트 상태가 워커 재시작에 살아남는다**

가장 혁신적인 부분입니다. 기존 에이전트는 서버가 재시작되거나 네트워크가 끊기면 진행 중인 작업이 전부 사라졌습니다. Temporal 통합에서는 에이전트 오케스트레이션(루프·도구 선택·핸드오프)이 Temporal Workflow 안에서 실행되고, 모델 호출만 Activity로 분리됩니다. 덕분에 모델 API 호출이 실패해도 자동으로 재시도되고, Workflow 재실행 시 이미 성공한 Activity는 다시 실행하지 않습니다(deterministic replay). 공식 문서 인용: *"Your agents survive Worker restarts and can run for extended periods without losing state."* 이것은 단순 기능이 아니라 패러다임 전환입니다 — 에이전트가 인프라 의존성에서 해방됩니다.

**4. Structured Outputs가 에이전트 신뢰성을 결정한다**

`output_type`을 지정하면 SDK는 모델이 해당 스키마에 맞는 JSON을 생성할 때까지 내부 루프를 돌립니다. JSON 모드·함수 호출·스키마 검증이 모두 SDK 내부에서 자동 처리됩니다. 에이전트가 "예, 처리했습니다"라는 자연어가 아니라 `{"status": "completed", "order_id": "ORD-1234"}` 형태의 검증된 구조로 응답하게 만드는 핵심 장치입니다. 비서앱·ERP에서 에이전트 출력이 다음 단계 자동화로 흘러가려면 이 패턴이 필수입니다.

**5. 프로덕션 다중 에이전트 예제 — 포트폴리오 협업 노트북**

OpenAI Cookbook에는 멀티에이전트 포트폴리오 협업 예제가 공개돼 있습니다. 리서치 에이전트·리스크 분석 에이전트·포트폴리오 최적화 에이전트가 Manager 패턴으로 협업하는 구조입니다. 각 에이전트는 독립적 도구(웹 검색·계산기·데이터 API)를 보유하고, 매니저 에이전트는 `agents as tools` 방식으로 서브에이전트를 호출합니다. 이 패턴은 와당탕 ERP에서 "발주 에이전트 → 재고 에이전트 → 회계 에이전트"로 완벽하게 이식됩니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱에서 가장 오래 실행되는 흐름(예: 주간보고 생성, 발주서 처리)을 찾아 "이 흐름이 서버 재시작으로 중단되면 어떻게 되는가?"를 한 줄로 기록합니다. 이게 Temporal 통합의 필요성을 체감하는 첫걸음이며, frontmatter `micro_action`과 동일합니다.

**이번 주 1-2시간 (mid)**: OpenAI Agents SDK를 로컬에 설치하고, ERP의 발주 흐름을 Manager 패턴으로 모델링해봅니다. 3개 서브에이전트(재고확인 에이전트, 공급사 조회 에이전트, 발주서 생성 에이전트)를 각각 `Agent(name=..., instructions=..., tools=[...])`로 정의하고, 매니저 에이전트가 이들을 `agents as tools`로 호출하는 코드 스니펫 작성.

```python
from agents import Agent, Runner

inventory_agent = Agent(
    name="재고확인 에이전트",
    instructions="현재 재고 데이터를 확인하고 발주 필요 여부를 판단합니다.",
    tools=[check_inventory_tool]
)

supplier_agent = Agent(
    name="공급사 조회 에이전트",
    instructions="최적 공급사와 단가를 조회합니다.",
    tools=[query_supplier_tool]
)

manager_agent = Agent(
    name="발주 오케스트레이터",
    instructions="재고 상황을 확인하고 공급사를 조회해 최적 발주서를 생성합니다.",
    agents_as_tools=[inventory_agent, supplier_agent]
)

result = Runner.run_sync(manager_agent, "이번 주 발주 처리해줘")
```

**이번 달 실험 (macro)**: 비서앱의 실제 장기 실행 워크플로우 1개를 Temporal 통합 패턴으로 리팩터링합니다. 대상: 매주 자동으로 실행되는 보고서 생성 루틴. 목표 지표: (1) 워커 재시작 후 이어서 실행 성공률 100%, (2) OpenAI API 호출 실패 시 자동 재시도 횟수 기록, (3) 워크플로우 실행 시간 대비 API 비용 절감률 측정.

## 한국 솔로 운영자 맥락에서 주의

**"우선 동작하게 만들고 나중에 내구성 추가"는 함정입니다.** Temporal 통합은 설계 초기에 넣어야 합니다. 이미 완성된 에이전트 코드에 Temporal을 사후 추가하면 구조를 전부 뜯어고쳐야 합니다. 와당탕 비서앱·ERP가 아직 초기 단계라면 지금이 Temporal 패턴을 심을 적기입니다.

**Temporal은 오버엔지니어링이 될 수도 있습니다.** 30초 이내 완료되는 단순 요청-응답 에이전트에는 Temporal이 오버킬입니다. 적용 기준: 실행 시간이 1분 이상이거나, 외부 API 의존성이 3개 이상이거나, 중간 결과를 사람이 검토해야 하는 Human-in-the-loop 흐름이면 투자 가치가 있습니다.

## 더 깊이 보려면

- [OpenAI Agents SDK 공식 핸드오프 문서](https://openai.github.io/openai-agents-python/handoffs/)
- [Temporal × OpenAI 통합 GA 발표](https://temporal.io/blog/announcing-openai-agents-sdk-integration)
- [Temporal + OpenAI 프로덕션 가이드](https://docs.temporal.io/ai-cookbook/openai-agents-sdk-python)
- [OpenAI Cookbook 멀티에이전트 포트폴리오 예제](https://cookbook.openai.com/examples/agents_sdk/multi-agent-portfolio-collaboration/multi_agent_portfolio_collaboration)
- [Agentic Governance 가이드](https://developers.openai.com/cookbook/examples/partners/agentic_governance_guide/agentic_governance_cookbook)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: 에이전트를 만들어서 자동화했더니, 서버가 새벽에 재시작되면서 진행 중이던 주간 보고서가 절반만 완성된 채 사라졌다. 아무도 몰랐다. 다음날 아침에야 텅 빈 보고서를 발견했다.
- **숫자**: Temporal × OpenAI 통합 GA — 2026년 3월 23일. 에이전트가 인프라 사고로 실패하는 비율을 0%에 가깝게 줄이는 것이 목표. OpenAI Agents SDK는 단 5개 프리미티브로 전체 멀티에이전트 아키텍처를 커버한다.
- **삽질**: 초기 Swarm 프레임워크 시절 팀들이 "교육용"이라고 표기된 도구를 프로덕션에 가져다 썼다가, 서버 재시작 때마다 에이전트 상태가 날아가는 사고를 반복했다. OpenAI가 이를 보고 Temporal 통합 GA를 서둘렀다는 배경이 있다.
- **훅**: "에이전트가 밤새 일하는 동안 서버가 한 번 재시작됐습니다. 아침에 업무가 완료돼 있을까요, 아니면 처음부터 다시 시작됐을까요? 2026년 3월 이전이라면 후자입니다."
