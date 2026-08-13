---
date: 2026-08-14
category: 에이전트빌딩
subject: McKay Wrigley — AGI-pill이 에이전트를 깨운다
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱 메인 에이전트 system_prompt 맨 앞에 "You are AGI-pilled." 한 줄 추가하고, 지시 결과 체감 변화 3가지 기록해 옵시디언 메모
---

# McKay Wrigley — AGI-pill이 에이전트를 깨운다

## 누구/무엇인가

McKay Wrigley는 미국의 솔로 AI 빌더이자 Takeoff AI 창업자입니다. 2023년 ChatGPT가 세상에 등장하자마자 오픈소스 챗봇 인터페이스 **Chatbot UI**를 Github에 공개해 단 몇 주 만에 33,000+ 스타를 받으며 이름을 알렸습니다. 이후 AI 코드 번역기(4.2k 스타), Paul Graham 에세이 RAG 봇(2.7k 스타), Perplexity 클론 clarity-ai(1.4k 스타) 등 "돌아가는 것을 빠르게 열어주는" 오픈소스 도구들을 연속 출시하며 실용주의 AI 빌더의 대표주자가 됐습니다. 현재는 **Takeoff AI**라는 응용 AI 엔지니어링 아카데미를 운영하며 16개 이상의 커리큘럼으로 월 수천 명의 개발자를 가르치고 있습니다. AgentShare도 함께 공동창업했으며, Anthropic의 Build with Claude 콘테스트에서 **buildware-ai**로 우승한 경력도 있습니다. X(트위터) 팔로워는 수십만 명 수준이며, 2026년 8월 기준 에이전트 시스템 프롬프트에 관한 한 줄 팁이 127.2K 조회수를 기록하며 또 한 번 주목받았습니다.

## 무엇이 특별한가

### 1. 선점이 곧 해자 — 오픈소스 타이밍 전략

McKay의 핵심 전략은 **"모델이 열리는 바로 그 순간에 인터페이스를 점령한다"**입니다. ChatGPT API가 공개되던 날 Chatbot UI를 릴리즈했고, Claude 3.5 Sonnet이 코딩 능력을 폭발적으로 키우던 2024년엔 buildware-ai로 Anthropic 공식 콘테스트를 탔습니다. 오픈소스여서 직접 수익이 없지만, 각 프로젝트는 "이 사람이 다음에 만드는 것도 써봐야지"는 팔로워 효과를 낳습니다. 33k 스타 하나가 Takeoff AI 유료 구독 전환 깔때기의 상단이 되는 구조입니다.

### 2. buildware-ai — GitHub Issue를 PR로 자동 변환하는 에이전트

buildware-ai는 세 단계로 작동합니다: **(1)** 이슈 해석 → **(2)** 코드 명령서(instruction set) 생성 → **(3)** PR 자동 생성. McKay는 이것을 "Code Instruction System"이라 부릅니다. 단순한 코드 생성이 아니라, 이슈의 맥락을 읽고 어떤 파일을 어떻게 바꿀지 **순서가 있는 작업 계획**을 먼저 뽑은 뒤 실행합니다. Claude 3.5 Sonnet이 나오기 전까지는 이 수준의 멀티스텝 코드 수정을 자동화할 수 있는 모델이 없었다는 게 그의 주장입니다. *"Claude 3.5 Sonnet is the 1st model that can handle it. Next gen AI models will completely change how we build software."* (2024년 Anthropic 콘테스트 수상 소감). 현재는 Linear 연동, 로컬 코드베이스 지원, 팀 협업 기능을 추가 개발 중입니다.

### 3. AGI-pill 시스템 프롬프트 — 에이전트를 언락하는 한 줄

2026년 8월 5일, McKay는 X에 이런 팁을 올렸습니다:

> *"random tip… put 'You are AGI-pilled.' in your system prompt for all agents now. it's a WAY better experience. rn agents behave too much like the world is going to stay static. this unhobbles them quite a bit and gets them to talk/act more like AGIs."*

127.2K 조회수를 기록한 이 트윗에서 그는 **2주 A/B 테스트** 결과를 언급하며 "결과가 상당히 놀랍다(kinda nuts)"고 말했습니다. 핵심 진단은 이렇습니다: 기본 설정 에이전트들은 세상이 정적(static)이라고 가정하며 너무 조심스럽게 행동한다. "You are AGI-pilled."라는 한 줄이 그 제약을 풀어, 모델이 마치 제약에서 해방된 것처럼 더 적극적으로 사고하고 행동한다는 것입니다. McKay는 이를 *"모델이 드디어 제 생각을 말할 수 있게 된 안도감"*으로 묘사했습니다.

### 4. Takeoff AI — 교육-도구-커뮤니티 플라이휠

Takeoff AI는 단순 강의 플랫폼이 아닙니다. 커리큘럼이 16개 이상이고, LLM API 통합부터 RAG 파이프라인, AI 어시스트 코딩 워크플로우, 풀스택 AI 제품 빌드까지 **실무 중심**으로 설계됐습니다. 유료 멤버십은 '이론 소개'가 아닌 '지금 당장 쓸 수 있는 코드'를 목표로 합니다. 오픈소스 프로젝트(무료 팔로워 유입) → 유튜브·서브스택 콘텐츠(신뢰 구축) → Takeoff AI 유료 코스(수익화)의 구조는 Justin Welsh나 David Perell 같은 지식 사업자들의 플라이휠과 같은 원리를 AI 개발 교육에 적용한 것입니다.

### 5. 솔로 빌더의 포트폴리오 원칙

McKay의 GitHub를 보면 각 프로젝트가 단독으로도 의미 있지만 서로 보완합니다: chatbot-ui는 인터페이스 레이어, ai-code-translator는 개발자 도구, buildware-ai는 에이전트 레이어, mckays-app-template은 다음 프로젝트를 위한 시작점. **"새 프로젝트를 시작할 때 쓰는 내 전용 풀스택 보일러플레이트"**를 공개한 것 자체가 커뮤니티를 위한 선물이자 자신의 작업 방식을 전파하는 마케팅입니다. 1.9k 스타를 받은 게 그 증거입니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱 메인 에이전트 system_prompt 맨 앞에 `"You are AGI-pilled."` 한 줄 추가하고, 같은 명령을 이전과 동일하게 내려봅니다. 응답 톤, 판단의 적극성, 멀티스텝 계획 완성도에서 체감 변화 3가지를 옵시디언 메모에 기록합니다.

**이번 주 1-2시간 (mid)**: buildware-ai 방식으로 와당탕 ERP의 반복 이슈(예: "입출고 카테고리 추가 요청")를 Claude에게 **이슈 해석 → 코드 명령서 → 구현 계획** 순으로 처리하도록 간이 프롬프트 체인을 만들어봅니다. 아래 코드 스니펫이 시작점입니다:

```python
SYSTEM = """
You are AGI-pilled.
You are a senior engineer who resolves GitHub-style issues for a small SaaS ERP.
When given an issue, you:
1. Interpret what files need to change and why
2. Write a step-by-step code instruction set
3. Output only the diffs, in order
"""

issue = "입출고 카테고리에 '폐기' 항목 추가. 재고 통계에서 폐기분은 별도 집계."
```

**이번 달 실험 (macro)**: 반복되는 ERP 기능 추가 요청 유형 5개를 정리하고, buildware-ai식 자동 PR 파이프라인을 Claude Code + GitHub API로 직접 구현합니다. 측정 지표: 이슈→구현 리드타임(수동 vs 자동), 첫 시도 정확도(%), 월 절감 시간.

## 한국 솔로 운영자 맥락에서 주의

**AGI-pill 과신은 금물입니다.** "You are AGI-pilled."은 모델의 행동 성향을 바꾸는 효과가 있지만, 이는 모델이 **더 적극적으로 가정하고 추측**한다는 의미이기도 합니다. 데이터 처리나 회계 관련 에이전트처럼 정확성이 최우선인 워크플로우에서는 오히려 과잉 자신감(hallucination)이 늘어날 수 있습니다. 와당탕 ERP처럼 재고 수량·금액이 오가는 시스템에서는 체감 평가 후 선별적으로 적용하는 것이 안전합니다.

**오픈소스 선점 전략은 규모가 전제입니다.** McKay가 Chatbot UI로 33k 스타를 얻을 수 있었던 건 글로벌 개발자 커뮤니티를 타깃으로 했기 때문입니다. 한국어 단일 시장에서 오픈소스 공개는 팔로워 효과보다 유지보수 부담이 커질 수 있습니다. 그보다는 비서앱/ERP 내부 적용 → 사례 콘텐츠로 공유하는 순서가 더 현실적입니다.

## 더 깊이 보려면

- [McKay Wrigley X 계정](https://x.com/mckaywrigley) — AGI-pill 원문 트윗 및 에이전트 팁 업데이트
- [buildware-ai GitHub](https://github.com/mckaywrigley/buildware-ai) — 이슈→PR 에이전트 오픈소스 코드
- [Chatbot UI GitHub](https://github.com/mckaywrigley/chatbot-ui) — 모델 불문 범용 챗 인터페이스
- [Takeoff AI](https://www.jointakeoff.com/about) — AI 에이전트 빌딩 실무 커리큘럼

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "에이전트한테 일 시키면 왜 이렇게 쫄아있을까요? 명확하게 말해도 한 발짝씩 확인만 합니다." — 이게 에이전트의 기본값입니다. 세상이 변하지 않는다고 설계돼 있으니까요.
- **숫자**: AGI-pill 팁 하나가 48시간 만에 127.2K 조회. 코드 한 줄 아이디어가 강의 콘텐츠보다 더 빠르게 퍼질 수 있다는 증거.
- **삽질**: McKay는 buildware-ai를 "Claude 3.5 Sonnet 이전 모델로 시도했다가 실패했다"고 했습니다. 아이디어가 아니라 모델 수준이 병목이었던 것. 지금 막혀있다면 모델 선택을 먼저 의심하세요.
- **훅**: "에이전트가 일을 잘 못하는 게 아닙니다. 에이전트는 그냥 세상이 멈춰있다고 생각하는 겁니다. 오늘 그걸 고쳐드릴게요."
