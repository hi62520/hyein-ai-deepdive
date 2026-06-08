---
date: 2026-06-09
category: AI네이티브회사
subject: OpenAI 공식 에이전트 가이드 + Agents SDK — 단일 에이전트부터 시작하라
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱 또는 ERP의 가장 복잡한 워크플로우 하나를 골라 "단계별 도구 목록"을 메모장에 써보기 (멀티에이전트 분기가 필요한 시점이 어디인지 체크)
---

# OpenAI 공식 에이전트 가이드 + Agents SDK — 단일 에이전트부터 시작하라

## 누구/무엇인가

2025년 3월 11일, OpenAI는 개발자들을 위해 세 가지를 동시에 공개했습니다: **Responses API**, **내장 도구 세트(웹 검색·파일 검색·컴퓨터 사용)**, 그리고 **오픈소스 Agents SDK**. 이전의 실험적 Swarm 프레임워크를 완전히 대체하는 프로덕션 급 멀티에이전트 빌딩 툴킷입니다. 같은 시기 공개된 공식 PDF 가이드 "A Practical Guide to Building Agents"는 지금까지 가장 체계적인 에이전트 설계 교과서로 통용되고 있습니다. GitHub의 `openai/openai-agents-python` 리포지토리는 출시 약 14개월 만에 **★ 27,000 / Fork 4,200**을 넘어섰고, 2026년 5월 26일에 v0.17.4가 출시될 만큼 업데이트가 지속됩니다. 가장 중요한 특징 하나: 이 SDK는 OpenAI 모델 전용이 아닙니다. 100개 이상의 LLM(Anthropic Claude, Google Gemini, Llama, Mistral 등)과 호환되도록 설계됐습니다.

## 무엇이 특별한가

### 1. "단일 에이전트 먼저" 원칙 — 복잡성을 무기로 삼지 말 것

OpenAI 가이드의 핵심 철학은 반직관적입니다. **"멀티에이전트를 기본 설정으로 쓰지 말라"**는 것입니다. 가이드는 명시적으로 말합니다: *"A single agent can handle many tasks by incrementally adding tools—keeping complexity manageable and simplifying evaluation and maintenance."* 즉, 도구를 하나씩 붙여 단일 에이전트의 능력을 극대화하는 것이 먼저입니다. 멀티에이전트로 분기하는 시점은 두 가지 조건이 충족될 때입니다: 프롬프트에 조건 분기(if-then-else)가 지나치게 많아질 때, 그리고 에이전트가 도구를 반복적으로 잘못 선택할 때. 솔로 운영자에게는 특히 중요한 교훈입니다 — 복잡한 에이전트 그래프를 설계하는 데 쏟는 에너지가 실제 비즈니스 가치보다 훨씬 클 수 있습니다.

### 2. 네 가지 핵심 프리미티브: 에이전트·도구·핸드오프·가드레일

Agents SDK의 설계는 딱 네 가지 추상화로 이루어집니다.
- **Agent**: 지시(instruction) + 도구 목록 + 핸드오프 목록으로 정의된 LLM 단위.
- **Tool**: 외부 API, Python 함수, MCP 서버, 또는 OpenAI 내장 도구(웹 검색·파일 검색·컴퓨터 사용).
- **Handoff**: 에이전트 간 제어권 이전. 한 방향 전달이며 대화 컨텍스트가 함께 딸려 갑니다. 예: 고객 지원 봇에서 "결제 전문 에이전트 → 환불 전문 에이전트 → 에스컬레이션 에이전트" 체인.
- **Guardrail**: 입력·출력 유효성 검사. 브랜드 위반 발언, 시스템 프롬프트 유출, 민감 정보 전달 차단.

이 네 프리미티브는 의도적으로 최소한으로 설계됐습니다. 프레임워크 자체를 배우는 시간을 줄이고, 비즈니스 로직에 집중하게 만들기 위해서입니다.

### 3. 두 가지 오케스트레이션 패턴 — Manager vs. Decentralized

가이드는 멀티에이전트 시스템의 오케스트레이션을 두 가지로 분류합니다.

**Manager 패턴**: 중앙 LLM("매니저")이 전체 흐름을 지휘하며 도구 호출을 통해 하위 에이전트에게 작업을 위임합니다. 병렬 실행이 자연스럽고, 전체 진행 상황이 한 곳에서 가시화됩니다. 복잡한 리서치 파이프라인이나 리포트 생성 워크플로우에 적합합니다.

**Decentralized(Handoff) 패턴**: 에이전트가 완료되면 다음 에이전트에게 컨텍스트를 넘기는 체인 구조. 고객 CS 봇처럼 명확한 단계적 흐름이 있는 경우에 최적화됩니다. 각 에이전트가 자신이 잘하는 영역만 담당하므로 프롬프트가 훨씬 단순해집니다.

와당탕연구소의 비서앱/ERP는 두 패턴의 혼합이 이상적입니다: 일정 파악 → 스케줄 조율 → 메모 저장은 핸드오프 체인, 여러 소스에서 동시 정보 수집은 Manager 패턴.

### 4. Human-in-the-Loop: 두 가지 트리거만 기억하면 된다

에이전트가 완전 자율화되면 안 되는 상황이 반드시 생깁니다. 가이드는 두 가지 개입 트리거를 제시합니다: **(1) 실패 임계값 초과** — 에이전트가 동일 의도를 여러 번 파악하지 못하면 인간으로 에스컬레이션. **(2) 고위험 액션** — 돌이킬 수 없거나 민감한 행동(결제, 삭제, 외부 발송)은 일시 정지 후 승인 대기. Agents SDK는 이를 코드 레벨에서 `approval` 메커니즘으로 구현합니다 — 모델이 도구 호출을 제안하지만 런너가 실제 실행 전에 멈추고 사람의 confirm을 기다립니다. 솔로 운영자에게는 이 패턴이 결정적입니다: 에이전트가 24시간 돌아가더라도 돈이 나가는 순간·외부에 무언가가 전송되는 순간만큼은 반드시 사람이 최종 확인하는 루프를 남겨야 합니다.

### 5. Responses API + 내장 도구: 세 줄로 웹 검색이 가능해졌다

Responses API는 기존 Chat Completions의 단순함과 Assistants API의 도구 사용 능력을 통합한 새 엔드포인트입니다. 특히 **내장 도구 세 가지** — 웹 검색(Web Search), 파일 검색(File Search), 컴퓨터 사용(Computer Use) — 를 별도 함수 없이 파라미터 한 줄로 활성화할 수 있습니다. GPT-4o와 gpt-4o-mini에서 웹 검색 도구를 켜면 에이전트가 실시간 인터넷 정보를 직접 가져옵니다. ERP에 "오늘 업계 뉴스 요약 후 CRM 노트에 자동 저장" 기능을 만들 때 외부 API 연동 없이도 가능해지는 이유입니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱 또는 ERP에서 가장 복잡한 워크플로우 하나를 선택해, 지금 단일 에이전트가 처리하기에 "조건 분기가 너무 많은" 지점을 메모장에 적어보세요. "if 주문 확인 → else 환불 → else 재발송" 같은 분기가 3개 이상이면 멀티에이전트 분리 시점입니다. 이 목록이 OpenAI Agents SDK 적용의 출발점이 됩니다.

**이번 주 1-2시간 (mid)**: `pip install openai-agents` 후, 비서앱의 "일정 조율" 시나리오를 핸드오프 패턴으로 프로토타이핑. 에이전트 두 개(일정 파악 에이전트 + 리마인더 발송 에이전트)를 코드 20줄로 연결하는 것부터 시작합니다.

```python
from agents import Agent, Runner

schedule_agent = Agent(
    name="ScheduleReader",
    instructions="오늘 캘린더에서 회의·마감 목록을 추출하라.",
    tools=[calendar_tool],
    handoffs=[reminder_agent]
)

reminder_agent = Agent(
    name="ReminderSender",
    instructions="받은 일정 목록을 기반으로 텔레그램 리마인더를 발송하라.",
    tools=[telegram_tool]
)

result = await Runner.run(schedule_agent, "오늘 일정 정리하고 알림 보내줘")
```

**이번 달 실험 (macro)**: ERP의 "발주 → 확인 → 결제 승인" 3단계 워크플로우를 Decentralized Handoff 패턴으로 재구현. Human-in-the-loop을 결제 단계에만 적용. 측정 지표: ① 워크플로우 완료 시간(기존 대비 단축률), ② 오승인율(Human-in-the-loop 거부 횟수), ③ 에러 에스컬레이션 빈도.

## 한국 솔로 운영자 맥락에서 주의

**"멀티에이전트 = 더 스마트한 AI"라는 착각을 경계하세요.** OpenAI 가이드가 명시하듯, 에이전트를 쪼갤수록 오케스트레이션 복잡도가 기하급수적으로 늘어납니다. 와당탕연구소처럼 혼자 모든 것을 유지보수해야 하는 구조에서는 에이전트 체인 하나가 6개월 뒤 블랙박스가 될 수 있습니다. "단일 에이전트에 도구만 추가해도 충분하다"는 기본기를 항상 먼저 검증하세요.

**OpenAI 모델 종속 비용도 계산하세요.** Responses API의 내장 도구(웹 검색 등)는 편리하지만 호출당 과금입니다. 비서앱이 하루 수십 번 웹 검색을 자동으로 실행한다면 월별 비용이 예상 밖으로 커질 수 있습니다. 프리미티브를 최소화하고, 자주 쓰는 정보는 캐싱 전략을 병행하세요.

## 더 깊이 보려면

- [OpenAI Agents SDK GitHub (★27K)](https://github.com/openai/openai-agents-python)
- [OpenAI: New tools for building agents (2025.03)](https://openai.com/index/new-tools-for-building-agents/)
- [OpenAI API Docs — Agents 오케스트레이션 & 핸드오프](https://developers.openai.com/api/docs/guides/agents/orchestration)
- [OpenAI API Docs — 가드레일 & Human Review](https://developers.openai.com/api/docs/guides/agents/guardrails-approvals)
- [OpenAI Cookbook — Deep Research API with Agents SDK](https://cookbook.openai.com/examples/deep_research_api/introduction_to_deep_research_api_agents)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: 에이전트를 여러 개 만들수록 "어느 에이전트가 왜 이 결정을 했는지" 알 수 없게 된다. 디버깅 시간이 기능 개발 시간보다 길어지는 역전 현상이 솔로 운영자에게 가장 치명적이다.
- **숫자**: GitHub ★ 27,000 / Fork 4,200, 출시 14개월 만. 100개 이상 LLM 지원. v0.17.4까지 지속 업데이트(2026.05).
- **삽질**: 초기 Swarm(실험적 전신 프레임워크)을 프로덕션에 쓰다가 업그레이드 경로 없이 막힌 팀들이 속출 → OpenAI가 Agents SDK로 완전 교체한 이유. 실험용 프레임워크는 프로덕션 코드베이스에 함부로 올리면 안 된다는 교훈.
- **훅**: "에이전트가 많을수록 더 똑똑해진다고 생각했다면, OpenAI의 공식 입장은 정반대입니다 — '단일 에이전트부터 시작하라.'"
