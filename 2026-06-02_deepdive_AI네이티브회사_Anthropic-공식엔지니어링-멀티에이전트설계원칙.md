---
date: 2026-06-02
category: AI네이티브회사
subject: Anthropic 공식 엔지니어링 — "단순한 것이 작동한다"
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱에서 가장 자주 쓰는 반복 프롬프트 하나를 instructions.md + examples/ 폴더 구조(Agent Skill 형식)로 분리해 저장해보기
---

# Anthropic 공식 엔지니어링 — "단순한 것이 작동한다"

## 누구/무엇인가

Anthropic은 2021년 설립 이후 연간 10배 성장을 이어가는 AI 안전 연구 기업이자, Claude 모델 패밀리의 개발사입니다. 대표님이 매일 Claude Code로 비서앱·ERP를 구축하고 있는 그 도구를 만드는 곳입니다. 이 회사의 특이한 점은 외부 개발자들에게 어떻게 잘 쓰라고 가르치는 데 상당한 공을 들인다는 것입니다. 2024-2026년 사이 Anthropic 엔지니어링 블로그(anthropic.com/engineering), 공식 리서치 가이드(anthropic.com/research/building-effective-agents), Claude Cookbook(GitHub 44,000+ stars), 그리고 2026년 Agentic Coding Trends Report까지 연속으로 발행하며 "에이전트를 제대로 만드는 법"에 대한 가장 밀도 높은 공개 자료를 만들어냈습니다. 단순히 마케팅이 아니라, 자신들이 내부 시스템(Claude Research 등)을 구축하면서 얻은 삽질과 교훈을 그대로 문서화한 것입니다. 솔로 운영자 입장에서 이 자료들은 수백만 달러짜리 사내 실험 결과를 무료로 훔쳐보는 것과 같습니다.

## 무엇이 특별한가

### 1. "단순한 것이 작동한다" — 핵심 철학

Anthropic이 수십 개의 성공한 AI 구현 사례를 분석해 낸 결론은 놀라울 만큼 반직관적입니다. "The most effective AI agent systems follow surprisingly simple patterns." 복잡한 프레임워크보다 단순한 조합 패턴이 실제로 더 잘 작동한다는 것입니다. 이들이 정리한 핵심 패턴은 5가지입니다: (1) **프롬프트 체이닝** — 복잡한 작업을 순차 단계로 쪼개기, (2) **라우팅** — 입력 유형에 따라 다른 처리 경로로 분기, (3) **병렬화** — 독립적인 작업을 동시 실행, (4) **오케스트레이터-워커** — 리드 에이전트가 서브에이전트에게 위임, (5) **평가자-최적화자** — LLM-as-a-judge 루프. 이 원칙을 대표님의 비서앱 관점에서 읽으면, "처음부터 멀티에이전트 아키텍처를 설계하지 말고, 단일 프롬프트 체인이 한계를 드러낼 때 패턴 하나씩 추가하라"는 뜻입니다.

### 2. 실전 숫자: 멀티에이전트 리서치 시스템 실험

2025년 6월, Anthropic 엔지니어링 블로그에 "How we built our multi-agent research system"이 게재됩니다. Claude Research 기능을 만든 과정을 그대로 공개한 문서입니다. 핵심 결과: Claude Opus 4를 Lead Researcher(오케스트레이터)로, Claude Sonnet 4를 서브에이전트들로 구성한 멀티에이전트 시스템이 단일 에이전트 Claude Opus 4를 **90.2%** 앞섰습니다. 복잡한 쿼리 처리 시간도 최대 90% 단축됐습니다. 구조는 이렇습니다: Lead Researcher가 쿼리를 분석해 전략을 수립하고, 동시에 3-5개 서브에이전트를 생성합니다. 각 서브에이전트는 병렬로 도구를 호출하고 결과를 공유 파일시스템에 씁니다. 마지막으로 Citation Agent가 모든 결과를 처리해 출처를 정확히 연결합니다. "초기 에이전트들은 단순한 쿼리에 50개 서브에이전트를 생성하거나, 존재하지 않는 출처를 끝없이 찾아 헤매는 실수를 했다." 이 문제의 해법은 복잡한 코드가 아니라 **프롬프트 엔지니어링**이었습니다. 규칙을 명확히 박아넣는 것: 단순 사실 확인은 에이전트 1개, 직접 비교는 2-4개, 복잡한 리서치는 10개 이상.

### 3. MCP + Agent Skills — 표준 레이어의 완성

Anthropic의 공개 전략은 단순한 가이드 배포를 넘어 인프라 표준화로 나아갔습니다. 2024년 11월 발표된 **Model Context Protocol(MCP)**은 에이전트가 외부 도구와 연결하는 방식의 사실상 표준이 됐고, 2026년 Agentic AI Foundation에 기증하며 오픈 거버넌스로 넘겼습니다. 그리고 2025년 말에 나온 **Agent Skills**는 MCP의 상위 레이어입니다. MCP가 에이전트에게 도구를 주는 것이라면, Skills는 에이전트에게 플레이북을 주는 것입니다. Skills는 instructions.md + examples 폴더로 구성되는 모듈형 지식 패키지입니다. 한 번 정의하면 반복 사용이 가능하고, 2026년 3월에 공개 표준(agentskills.io)으로 오픈소스화됐습니다. Atlassian, Canva, Figma, Notion, Sentry 등이 첫 파트너로 참여했습니다.

### 4. 도구 설명서가 성능을 결정한다

Anthropic Cookbook에서 나온 덜 알려진 발견이 있습니다. 팀이 "tool-testing agent"를 실행해 결함 있는 도구 설명을 찾아 다시 작성했더니, 이후 에이전트들의 작업 완료 시간이 **40% 단축**됐습니다. 다시 말해, 에이전트 성능의 상당 부분은 모델이 아니라 도구 설명문(tool description)의 품질에 달려 있습니다. 솔로 운영자가 Claude Code로 MCP 서버를 붙일 때, 툴 이름과 설명에 투자하는 15분이 이후 수십 시간의 에이전트 오류를 줄입니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱에서 가장 자주 쓰는 반복 프롬프트 하나를 Agent Skill 형식으로 분리합니다. `skills/주문-요약/` 폴더를 만들고 `instructions.md`에 목적·출력 형식·금지 사항을 쓰고, `examples/` 폴더에 예시 입출력 1-2개를 넣습니다. 이 구조 자체가 micro_action의 실체입니다.

**이번 주 1-2시간 (mid)**: 현재 비서앱의 가장 느린 작업 흐름 하나를 "프롬프트 체이닝 → 오케스트레이터-워커" 두 단계로 분해해 프로토타입을 만들어봅니다. 예를 들어 "주문 접수 → 재고 확인 → 응답 초안 작성"이 지금 하나의 긴 프롬프트라면, 3개 단계로 쪼개고 중간 단계에 게이트(확인 조건)를 추가합니다.

```python
# 오케스트레이터-워커 미니 패턴
def process_order(order_text):
    # 1단계: 분석 (프롬프트 체이닝)
    parsed = claude("주문 파싱: " + order_text, model="haiku")
    # 게이트: 필수 필드 확인
    if not parsed.get("item") or not parsed.get("quantity"):
        return {"error": "필수 정보 누락"}
    # 2단계: 병렬 서브에이전트 (재고 + 가격 동시 확인)
    stock, price = parallel([
        claude("재고 확인: " + parsed["item"], tools=[inventory_tool]),
        claude("가격 조회: " + parsed["item"], tools=[price_tool])
    ])
    # 3단계: 응답 합성
    return claude(f"응답 작성: {parsed}, 재고={stock}, 가격={price}")
```

**이번 달 실험 (macro)**: 비서앱의 1개 워크플로우를 완전히 멀티에이전트로 전환하고, 응답 정확도와 처리 시간을 측정합니다. Anthropic의 기준(단순 → 1 에이전트, 비교 → 2-4개, 복합 → 10개 이상)을 적용해 어떤 구조가 와당탕의 실제 케이스에 맞는지 데이터로 확인합니다.

## 한국 솔로 운영자 맥락에서 주의

**"90% 성능 향상"을 맹신하지 말 것.** 이 수치는 Anthropic의 대규모 리서치 시스템 기준입니다. 서브에이전트를 늘릴수록 토큰 비용과 디버깅 복잡도가 선형 이상으로 증가합니다. 혼자 운영하는 비서앱에서 10개 서브에이전트는 오히려 장애 포인트가 10개라는 뜻입니다. Anthropic 자신도 "작동하면 에이전틱 시스템 추가를 고려하라"고 명시합니다. 단순 체인으로 충분한 케이스에서 억지로 멀티에이전트 구조를 도입하면, 대표님 혼자 유지보수할 수 없는 복잡계가 됩니다.

**Agent Skills 파트너 목록이 B2B 대기업 중심임을 인식할 것.** Atlassian·Figma·Notion은 이미 수십 명의 엔지니어링 팀이 있는 곳입니다. 솔로 운영자는 공식 Skills 디렉터리를 "따라 만드는 것"이 아니라, 이 구조를 참고해 자신만의 사내(internal) Skills를 만드는 쪽으로 적용해야 합니다.

## 더 깊이 보려면

- [Anthropic Engineering Blog](https://www.anthropic.com/engineering)
- [Building Effective Agents (원문)](https://www.anthropic.com/research/building-effective-agents)
- [How we built our multi-agent research system](https://www.anthropic.com/engineering/multi-agent-research-system)
- [Claude Cookbook GitHub](https://github.com/anthropics/anthropic-cookbook)
- [Agent Skills 공개 표준](https://thenewstack.io/agent-skills-anthropics-next-bid-to-define-ai-standards/)
- [MCP + Agent Skills 개요](https://bytebridge.medium.com/model-context-protocol-mcp-and-agent-skills-empowering-ai-agents-with-tools-and-expertise-bd4dbe3f2f00)
- [2026 Agentic Coding Trends Report](https://resources.anthropic.com/hubfs/2026%20Agentic%20Coding%20Trends%20Report.pdf)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: 에이전트를 만들었더니 너무 복잡해서 아무도 유지보수 못 함. 솔로 운영자에게는 아무도 고쳐줄 사람이 없음.
- **숫자**: Anthropic 자체 시스템에서 멀티에이전트가 단일 에이전트 대비 90.2% 성능 향상, 복잡한 리서치 처리 시간 최대 90% 단축. 도구 설명문 개선 하나로 완료 시간 40% 단축.
- **삽질**: 초기 에이전트가 단순 쿼리에 50개 서브에이전트를 생성하는 오버엔지니어링. 해법은 새로운 모델이 아니라 프롬프트 1줄("단순 사실 확인은 1개 에이전트만 써라").
- **훅**: "Anthropic은 1,000명 이상의 엔지니어가 있습니다. 그들이 삽질하고 쓴 문서가 공짜로 공개돼 있는데, 읽지 않는 건 그냥 손해입니다."
