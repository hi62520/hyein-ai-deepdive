---
date: 2026-09-11
category: 에이전트빌딩
subject: IndyDevDan — 상위 2%의 에이전트 자율성 설계도
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱의 Claude 호출 중 하나를 Closed-Loop Prompt 패턴으로 리팩터링 — 에이전트가 자기 출력을 검증하고 재시도하는 루프를 30분 안에 붙여보기
---

# IndyDevDan — 상위 2%의 에이전트 자율성 설계도

## 누구/무엇인가

IndyDevDan은 본명 Dan Disler, 10년 이상 경력의 시니어 소프트웨어 엔지니어이자 제너레이티브 AI 도구의 얼리어답터입니다. YouTube 채널 구독자 10만 명 이상을 보유하고 있으며, agenticengineer.com을 운영하면서 "Living Software — 소프트웨어가 스스로 일한다"는 철학 아래 에이전트 코딩 교육 콘텐츠와 강의를 만들고 있습니다. 단순한 AI 코딩 팁이 아니라, 프로덕션 수준의 에이전트 워크플로우 아키텍처를 가르치는 것이 차별점입니다. 2026년 2월에 발행한 "Top 2% Agentic Engineering — Roadmap for 2026"은 10만 회 이상 조회되며 에이전트 엔지니어링 커뮤니티에서 기준 문서처럼 읽히고 있습니다. 가장 최근 화제가 된 콘텐츠는 2026년 5월 27일 공개된 유튜브 영상 "Agentic Workflows Have Changed EVERYTHING in 2026 (DEATH Of The Senior Dev?)"입니다.

## 무엇이 특별한가

**1. "상위 2%의 시스템"이라는 프레임**

IndyDevDan이 2026년 초에 제시한 핵심 테제는 날카롭습니다. "100명의 엔지니어가 2026년을 시작했다. 98명은 AI 코딩 도구를 쓴다. 소수는 커스텀 에이전트를 만든다. 단 2명만이 시스템을 만드는 시스템을 만든다." ("Out of one hundred engineers entering 2026, ninety-eight will use AI coding tools, a handful will build custom agents, and only two will build the system that builds the systems.") 도구를 쓰는 것과 도구를 설계하는 것의 차이. 대표님이 비서앱·ERP를 Claude Code로 직접 풀스택 개발하는 방식은 이미 그 2%의 영역에 진입한 전략입니다.

**2. 12 Leverage Points — 에이전트 자율성을 체계적으로 높이는 12개 레버**

단순히 프롬프트를 개선하는 수준을 넘어, 자율성을 12개 축에서 체계적으로 측정·개선하는 프레임워크입니다. 핵심 4개(Context·Model·Prompt·Tools)에서 시작해 Standard Output·Types·Tests·Architecture·Verification 등으로 확장됩니다. 중요한 점은 이것이 체크리스트가 아니라 **KPI 관리 체계**라는 것입니다. "에이전트가 얼마나 잘 작동하는가"를 주관적으로 평가하는 대신, 12개 레버 각각을 0-5점 스케일로 평가해 병목을 찾아냅니다. 에이전트가 자꾸 틀리면 Model 레버, 지시를 못 따르면 Prompt 레버, 외부 정보를 못 불러오면 Context 레버를 건드립니다.

**3. ZTE + PITER Model — "루프 밖으로 완전히 나가는" 아키텍처**

IndyDevDan의 성숙도 곡선은 세 단계입니다. "In Loop(항상 감독)" → "Out Loop(가끔 감독)" → "ZTE — Zero-To-Excellent(완전 자율)". ZTE는 에이전트 워크플로우의 가장 흔한 실패 패턴을 구조적으로 제거하는 설계 원칙입니다. 여기에 PITER Model이 맞물립니다. PITER는 단일 에이전트를 넘어 멀티에이전트 파이프라인을 완전 자동화하는 오케스트레이션 패턴으로, 인간이 루프 안에서 감독하지 않아도 에이전트들이 서로 검증·수정하는 구조를 만들어 줍니다. 14모듈, 6.5시간짜리 "Tactical Agentic Coding" 강의의 후반부가 이 영역을 다룹니다.

**4. Closed-Loop Prompting — 에이전트가 자기 실수를 고친다**

IndyDevDan이 가장 실용적이라고 강조하는 패턴은 Closed-Loop Prompting입니다. 에이전트가 작업을 완료한 뒤, 자신의 출력을 정해진 기준으로 검증하고 기준을 통과하지 못하면 자동으로 재시도하는 루프입니다. "Closed Loop Prompts ensure agents correct their own work so you don't have to." 이 설계 하나가 감독 비용을 극적으로 낮춥니다. AFK Agent(Away From Keyboard Agent)의 핵심 메커니즘이 바로 이 Closed-Loop입니다.

**5. 2026년 데이터: 도구는 넘쳤고 판단은 부족했다**

2026년 Q2 기준, 전체 코드의 52%가 AI 생성 코드입니다(Q1 34% → Q2 52%). 개발자들은 주당 4-6시간을 절약했지만, Developer Experience Index는 오히려 하락했고 PR 사이즈는 두 배로 커졌으며 Change Confidence(변경 자신감)는 6.1% 감소했습니다. IndyDevDan의 표현으로 "절약된 시간이 혁신으로 전환되지 않고 있다." 도구가 넘쳤고, 에이전트를 설계하는 역량이 부족했습니다. "Your value as an engineer scales directly with the amount of compute you can harness." — 활용할 수 있는 컴퓨팅 파워에 비례해 엔지니어의 가치가 결정된다는 뜻이고, 이건 도구 사용자가 아니라 도구 설계자에게만 해당하는 말입니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱에서 가장 자주 실패하는 Claude 호출 하나를 선택합니다. 해당 호출 직후 "방금 생성한 결과가 기준 [조건]을 만족하는지 스스로 검증하고, 미달하면 이유를 포함해 재생성하라"는 검증 루프 프롬프트를 붙여봅니다. Closed-Loop Prompting의 가장 단순한 형태이며 30분 안에 테스트 가능합니다.

**이번 주 1-2시간 (mid)**: 12 Leverage Points 체크리스트를 ERP/비서앱의 현재 에이전트 호출에 적용해봅니다. Context·Model·Prompt·Tools 4개 레버를 각각 1-5점으로 자가 평가하고, 가장 낮은 레버 하나를 개선하는 코드를 작성합니다. 예를 들어 Context가 약하다면 CLAUDE.md에 운영 컨텍스트를 구조화해서 추가하는 것부터 시작할 수 있습니다.

```python
# Closed-Loop 패턴 예시 (비서앱 ERP 호출에 삽입)
def call_with_verification(prompt: str, criteria: str, max_retry: int = 2) -> str:
    for attempt in range(max_retry + 1):
        result = claude_call(prompt)
        verification = claude_call(
            f"아래 결과가 기준 [{criteria}]을 만족하는가? "
            f"만족하면 'PASS', 아니면 'FAIL: [이유]' 로 답하라.\n결과: {result}"
        )
        if "PASS" in verification:
            return result
        prompt = f"{prompt}\n\n이전 시도 실패 이유: {verification}\n이를 반영해 재생성하라."
    return result  # max_retry 후 마지막 결과 반환
```

**이번 달 실험 (macro)**: 와당탕 ERP에서 반복 실행되는 루틴 작업(예: 일간 리포트 생성, 고객 응답 초안 작성) 하나를 완전한 AFK Agent로 전환합니다. 측정 지표: (1) 수동 개입 횟수 — 목표 주 3회→0회, (2) 작업 완료 시간, (3) 결과 품질 5점 자가 평가. ZTE 성숙도를 "In Loop → Out Loop"까지 한 단계 진행하는 것을 목표로 삼습니다.

## 한국 솔로 운영자 맥락에서 주의

IndyDevDan의 콘텐츠는 미국 시니어 엔지니어를 대상으로 합니다. 12 Leverage Points나 PITER Model은 이미 에이전트 파이프라인이 어느 정도 구축된 팀에서 체계화하는 도구입니다. 대표님처럼 솔로로 운영하면서 ERP/비서앱을 동시에 개발하는 경우, 12개를 전부 최적화하려다 본업을 놓치는 위험이 있습니다. 한 번에 1개 레버에 집중하는 것이 현실적입니다. 또한 AFK Agent를 "완전 방치"로 해석하면 위험합니다. 에이전트가 고객 응대나 결제 관련 로직을 건드리는 경우, Closed-Loop의 검증 기준이 충분히 엄격하지 않으면 조용히 잘못된 결과를 반복 생성합니다. "AFK"는 감독 빈도를 줄이는 것이지 감독을 없애는 것이 아닙니다.

## 더 깊이 보려면

- [Top 2% Agentic Engineering — Roadmap for 2026](https://agenticengineer.com/top-2-percent-agentic-engineering)
- [Tactical Agentic Coding 강의 상세](https://agenticengineer.com/tactical-agentic-coding)
- [IndyDevDan VSCode Snippets (Skill·Subagent 템플릿)](https://gist.github.com/disler/d9f1285892b9faf573a0699aad70658f)
- [State of AI Coding — Engineering with Exponentials](https://agenticengineer.com/state-of-ai-coding/engineering-with-exponentials)
- [IndyDevDan YouTube](https://www.youtube.com/@indydevdan/videos)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: 에이전트를 쓰는데 계속 감독해야 한다. 결국 내가 더 바쁘다. AI가 나를 돕는 게 아니라 내가 AI를 돕는 것 같다.
- **숫자**: 2026년 Q2 기준 AI 생성 코드 52%. 개발자는 주 4-6시간 절약했는데 Change Confidence는 6.1% 하락. "절약된 시간이 혁신으로 전환되지 않는다."
- **삽질**: 12 Leverage Points를 한꺼번에 최적화하려다 어디도 제대로 못 건드리고, 결국 프롬프트만 길어지고 비용만 늘었다.
- **훅**: "100명 중 98명은 AI 도구를 쓴다. 2명만이 AI 도구를 만든다. 대표님은 지금 어느 쪽에 앉아 있습니까?"
