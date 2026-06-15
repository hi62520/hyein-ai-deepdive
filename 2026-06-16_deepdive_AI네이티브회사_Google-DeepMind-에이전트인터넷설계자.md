---
date: 2026-06-16
category: AI-Native 회사
subject: Google DeepMind — 에이전트 인터넷의 설계자
tags: [AI탐구, deepdive]
starred: false
micro_action: Gemini API Free Tier로 비서앱 메모 하나를 1M 토큰 컨텍스트로 요약하는 버튼 추가해보기 (5분 코딩)
---

# Google DeepMind — 에이전트 인터넷의 설계자

## 누구/무엇인가

Google DeepMind는 2023년 구글 브레인과 딥마인드가 합병해 탄생한 구글의 핵심 AI 연구·제품 조직입니다. CEO 데미스 하사비스(Demis Hassabis)가 이끌며 Gemini 모델 패밀리, AlphaFold, Co-Scientist 등 기초연구부터 제품까지 모두 책임집니다. 2024년 말 Gemini 2.0을 "에이전트 시대의 모델"로 선언하면서 단순한 LLM 공급사에서 **에이전트 생태계 인프라 회사**로 방향을 전환했습니다. 2025년 4월에는 Agent2Agent(A2A) 오픈 프로토콜을 발표해 150개 이상 기업이 프로덕션에서 사용 중이며, 2026년 구글 I/O에서 Gemini 3.5 Flash를 공개하며 벤치마크 1위를 탈환했습니다. 하사비스는 AGI 실현 시점을 2029~2030년으로 보며 이를 "species-level transition(종 단위의 전환)"이라 부릅니다.

## 무엇이 특별한가

### 1. "생각이 먼저"인 Gemini 2.5 Pro — 1백만 토큰 컨텍스트

Gemini 2.5 Pro는 CoT(Chain-of-Thought) 추론을 사후에 붙이지 않고 **아키텍처 설계 단계부터 내장**했습니다. 이른바 "thinking-native" 모델입니다. 성과도 수치로 증명됩니다: SWE-bench Verified 63.8%, AIME 2025 86.7%, WebDev Arena ELO 1415(1위). 무엇보다 실용적인 차별점은 **1백만 토큰 컨텍스트 윈도우**입니다. 개발자가 전체 코드베이스를 한 번에 붙여넣어 "어느 파일에서 버그가 날지?"를 물어볼 수 있습니다. 대표님의 비서앱 전체 DB 스키마 + 지난 3개월 주문 데이터를 통째로 던지고 "이번 달 병목은?"을 묻는 게 가능한 수준입니다.

### 2. Co-Scientist — 멀티에이전트 설계의 교과서

2025년 공개된 Co-Scientist는 과학 연구 가속화를 목적으로 Gemini 위에 구축된 멀티에이전트 시스템입니다. **Supervisor · Generation · Reflection · Ranking · Evolution · Proximity · Meta-review** 총 7개 전문 에이전트가 역할을 분담합니다. 자연어 연구 목표를 입력하면 에이전트들이 가설을 생성하고, 서로 논쟁하고, 진화시켜, 토너먼트 방식으로 최상위 가설을 산출합니다. 급성 골수성 백혈병 약물 재목적화, 간섬유증 신규 타깃 발굴, 항균제 내성 메커니즘 규명 등 3개 바이오메디컬 사례에서 초기 검증을 마쳤습니다. 핵심 교훈은 구조입니다: **하나의 만능 에이전트가 아니라, 역할이 분명한 작은 에이전트들의 협업 루프**가 품질을 만들어냅니다.

### 3. A2A 프로토콜 — 에이전트들의 인터넷 표준

2025년 4월 발표된 Agent2Agent(A2A) 프로토콜은 Google, LangChain, PayPal이 공동 개발해 Linux Foundation에 기증한 오픈 스탠다드입니다. HTTP(S) + JSON-RPC + Server-Sent Events 위에 쌓여서 **다른 플랫폼·다른 벤더로 만든 에이전트끼리 서로 발견하고 메시지를 주고받는** 규약입니다. MCP가 "에이전트 ↔ 도구/데이터"를 연결한다면, A2A는 "에이전트 ↔ 에이전트"를 연결합니다. 2026년 초 기준 Microsoft, AWS, Salesforce, SAP, ServiceNow가 프로덕션에서 A2A를 운영 중이며 참여 기업은 150곳을 넘었습니다. 구글이 이 표준을 오픈소스로 내놓은 이유는 Anthropic의 MCP와 비슷합니다: 표준을 쥔 곳이 생태계의 중력 중심이 되기 때문입니다.

### 4. Workspace Studio + Project Mariner — 코딩 없는 에이전트 빌더

2026년 구글 클라우드 넥스트에서 공개된 Google Workspace Studio는 Gmail·Docs·Sheets·Drive·Meet·Chat에 걸쳐 **자연어 한 줄로 에이전트를 만드는 노코드 플랫폼**입니다. "매주 금요일, 나에게 트래커 업데이트 알림 보내줘"라고 입력하면 Gemini가 자동화를 생성합니다. Asana, Jira, Mailchimp, Salesforce에도 연결되고 웹훅이나 Apps Script로 외부 API를 호출할 수 있습니다. Project Mariner는 Chrome 브라우저를 직접 제어하는 에이전트로, 커서를 움직이고 버튼을 누르고 폼을 채웁니다. 이 두 가지가 합쳐지면 **브라우저 작업 + 워크스페이스 자동화를 코드 한 줄 없이** 구현하는 루프가 완성됩니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: Gemini API 무료 티어(Google AI Studio)에서 비서앱의 메모 텍스트 50개를 한꺼번에 붙여넣고 "이번 주 반복된 고객 요청 패턴 3가지 추출"을 실행해 보세요. 1M 토큰 컨텍스트 덕분에 전체 히스토리를 자르지 않고 통째로 넣을 수 있습니다. 비서앱의 `메모 요약` 버튼 하나에 이 호출을 붙이면 반복 분석 작업이 사라집니다.

**이번 주 1-2시간 (mid)**: Co-Scientist의 7에이전트 구조를 **2에이전트 미니버전**으로 흉내 내봅니다. ERP에서 주문 데이터를 받아 "가설 생성 에이전트"가 재고 부족 원인 3개를 제시하고, "반박 에이전트"가 각각에 반례를 붙이는 루프를 Claude Code로 짭니다. 실제 Co-Scientist가 쓰는 토너먼트 랭킹 대신, 두 에이전트 간 주고받은 대화를 로그로 남기는 것만으로도 판단 품질이 눈에 띄게 달라집니다.

```python
# 예시 스니펫 — 2에이전트 debate loop
def run_debate(data: str, rounds: int = 2):
    hypothesis = generate_agent(f"주문 데이터:\n{data}\n\n재고 부족 원인 3가지 가설을 제시해줘.")
    for _ in range(rounds):
        critique = reflect_agent(f"가설:\n{hypothesis}\n\n각 가설의 반례나 약점을 지적해줘.")
        hypothesis = generate_agent(f"가설:\n{hypothesis}\n\n반박:\n{critique}\n\n가설을 개선해줘.")
    return hypothesis
```

**이번 달 실험 (macro)**: A2A + MCP 조합으로 비서앱 에이전트(고객 메모 처리)와 ERP 에이전트(재고·주문 조회)가 서로 대화하는 구조를 설계합니다. Anthropic MCP로 ERP DB를 도구로 노출하고, A2A 메시지 포맷으로 비서앱 에이전트가 ERP 에이전트에게 재고 조회를 위임하는 파일럿을 만듭니다. 측정 지표: 에이전트 간 왕복 1회에 걸리는 평균 시간과 오류율.

## 한국 솔로 운영자 맥락에서 주의

**구글 생태계 락인 리스크가 큽니다.** Workspace Studio는 Google Workspace 구독 안에서만 작동하고, A2A 프로토콜은 현재 Google의 인프라(Vertex AI 에이전트 엔진)와 긴밀하게 묶여 있습니다. 대표님처럼 Claude Code 풀스택으로 직접 시스템을 구축하는 경우, Anthropic MCP를 이미 쓰고 있다면 Google 쪽 A2A를 추가 도입할 때 두 프로토콜 간 변환 레이어 비용이 예상보다 클 수 있습니다.

**"에이전트 12개 평균" 수치는 대기업 기준입니다.** Google Cloud 보고서의 "조직당 에이전트 12개 운영" 통계는 수백 명 규모 기업 기준입니다. 솔로 운영자에게는 에이전트 수보다 **에이전트당 ROI**가 훨씬 중요합니다. 하나의 잘 설계된 에이전트가 12개의 어설픈 에이전트보다 낫습니다.

## 더 깊이 보려면

- [Gemini 2.5 기술 보고서 (arXiv)](https://arxiv.org/pdf/2507.06261)
- [Google I/O 2025: Gemini 업데이트](https://blog.google/innovation-and-ai/models-and-research/google-deepmind/google-gemini-updates-io-2025/)
- [Agent2Agent 프로토콜 개요 (Galileo)](https://galileo.ai/blog/google-agent2agent-a2a-protocol-guide)
- [A2A + MCP 비교 분석 (Koyeb)](https://www.koyeb.com/blog/a2a-and-mcp-start-of-the-ai-agent-protocol-wars)
- [Google Workspace Studio](https://workspace.google.com/studio/)
- [Demis Hassabis: AGI와 species-level transition (Axios)](https://www.axios.com/2026/05/26/deepmind-ceo-demis-hassabis)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: 비서앱이랑 ERP가 따로 놀아서 매번 복붙하는 게 하루 30분을 잡아먹는다 — 정확히 A2A가 해결하려는 문제입니다.
- **숫자**: A2A 프로덕션 도입 기업 150곳, Gemini 2.5 Pro SWE-bench 63.8%, 1M 토큰 컨텍스트(소설 7권 분량을 한 번에 읽는 수준).
- **삽질**: 구글은 2019년부터 LaMDA, PaLM, Bard를 만들었지만 OpenAI에 밀렸습니다. Gemini 2.5로 코딩 벤치마크 1위를 탈환하기까지 **에이전트 인프라 표준화(A2A)라는 우회로**를 택한 것이 반전 포인트였습니다.
- **훅**: "AI 에이전트가 서로 대화하는 인터넷이 이미 150개 기업에서 돌아가고 있습니다. 그 표준을 만든 게 구글이에요."
