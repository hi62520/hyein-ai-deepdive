---
date: 2026-05-29
category: 에이전트빌딩
subject: McKay Wrigley — 3개 에이전트 동시 실행, 이기는 놈 코드 채택
tags: [AI탐구, deepdive]
starred: false
micro_action: 터미널에서 Claude Code와 Gemini CLI를 동시에 열고, 비서앱의 작은 기능 하나를 두 에이전트에게 같은 프롬프트로 맡긴 뒤 결과물을 나란히 비교해본다
---

# McKay Wrigley — 3개 에이전트 동시 실행, 이기는 놈 코드 채택

## 누구/무엇인가

McKay Wrigley는 법학대학원을 그만두고 코딩 부트캠프에 등록한 뒤, 트위터에 학습 과정을 실시간 공개하면서 개발자 커리어를 시작한 솔로 AI 빌더입니다. GPT-3 초창기인 2020년 ARK Invest 팟캐스트에 출연해 "누구에게서든 무엇이든 배울 수 있다"는 AI 교사 비전을 소개했고, 이후 오픈소스 chatbot-ui를 출시해 GitHub에서 **33,300개 이상의 스타**를 받으며 AI 개발자 커뮤니티에서 이름을 알렸습니다.

현재는 Takeoff AI를 MagicLearn으로 리브랜딩하고, **25,000명 이상의 학습자**에게 AI 코딩 교육을 제공하고 있습니다. 단순한 강의 플랫폼이 아니라, AgentShare(에이전트 워크스페이스)와 Magic MCP(학습 특화 MCP 도구)를 직접 개발해 "배움 자체를 AI 네이티브로 재설계"하는 방향으로 피벗하고 있습니다. 2026년 현재 AI for Code와 AI for Work 두 개의 학습 트랙을 운영하며, 솔로 운영자로서 교육·도구·커뮤니티를 하나의 생태계로 엮고 있습니다.

---

## 무엇이 특별한가

### 1. "에이전트 경마" 워크플로우 — 모델을 고르지 않고, 레이스시킨다

McKay의 가장 독특한 전략은 코딩 에이전트를 하나만 쓰지 않는다는 점입니다. 터미널에서 `ai`라고 타이핑하면 Claude Code, Gemini CLI, Codex CLI 세 개가 **동시에 같은 창에서 동기화된 상태로 실행**됩니다. 음성으로 프롬프트를 입력하고 전송하면, Claude Opus 4, Gemini 2.5 Pro, OpenAI o3가 같은 태스크를 병렬로 처리합니다. 그가 하는 일은 세 결과물을 보고 "이기는 놈"의 코드를 채택하는 것뿐입니다.

> "My workflow to spin up 3 coding agents at once: type 'ai' in terminal, launches Claude Code, Gemini CLI, & Codex CLI — fully synced windows. Prompt w/ voice, hit send & watch. Now Claude Opus 4, Gemini 2.5 Pro, and OpenAI o3 work on task — you pick the winner."
> (2026년 트윗, 한국어 의역: "에이전트 3마리를 동시에 출발시키는 게 내 워크플로우다. 음성으로 프롬프트를 쏘고 결과 중 이기는 놈을 고른다.")

모델 충성도가 아닌 **결과 기반 선택**이라는 실용주의적 접근입니다.

### 2. 모델 편향 없는 평가 — "3개월 만에 80/20이 뒤집혔다"

McKay는 2026년 솔직한 자기 관찰을 공유했습니다. "코딩에서는 Claude 80%, GPT 20%로 쓰다가 3개월 만에 GPT 80%, Claude 20%로 바뀌었다. 솔직히 놀랍다." 하지만 동시에 "Claude는 비코딩 에이전트 작업에서는 여전히 GPT를 압도한다. Codex는 마치 엔지니어 같은 느낌"이라고 덧붙였습니다. 도구를 용도별로 분리해서 쓰는 이 사고방식은 대표님이 비서앱·ERP를 개발할 때도 그대로 적용할 수 있는 원칙입니다.

### 3. 하네스(harness)가 모델만큼 중요하다는 철학

McKay는 Anthropic의 Claude Agent SDK를 "AI 최고의 공공연한 비밀"이라고 불렀습니다.

> "An agent's harness matters almost as much as its model. If you have a bad harness, you may as well have a bad model. With the SDK you get a world-class agentic harness out-of-the-box."
> (한국어 의역: "에이전트의 하네스는 모델 자체만큼 중요하다. 하네스가 나쁘면 모델이 좋아도 소용없다.")

Alan Kay의 말을 비틀어 "모델을 진지하게 쓰는 사람은 자기만의 하네스를 만들어야 한다"고 말했고, Anthropic이 SDK를 통해 그것을 구현했다고 평가합니다.

### 4. 오픈소스 → 커뮤니티 → 유료 교육의 깔때기 설계

chatbot-ui라는 오픈소스 프로젝트가 GitHub에서 33K 스타를 받으면서 McKay의 이름이 알려졌고, 그 팔로워들이 Takeoff AI → MagicLearn의 유료 학습자로 전환됐습니다. 이 흐름은 Pieter Levels의 "빌딩 인 퍼블릭" 전략과 구조적으로 같습니다. 오픈소스로 신뢰를 쌓고, 그 신뢰를 교육 상품으로 수익화하는 솔로 운영자의 전형적인 패턴입니다.

### 5. MagicLearn = 강의 플랫폼이 아닌 AI 네이티브 교육 OS

MagicLearn의 가장 야심찬 부분은 Magic MCP입니다. 이것은 단순한 챗봇이 아니라 "AI 도구가 학습 컨텍스트를 직접 갖게" 만드는 MCP 레이어입니다. 학습자가 "Claude Code에서 어떤 hook을 써야 해?"라고 물으면, Magic MCP가 실제로 명령을 실행해 답을 보여줍니다. 영상을 보는 것이 아니라, AI와 함께 실시간으로 실행하는 구조입니다. AgentShare는 에이전트를 만들고, 공유하고, 자신의 컴퓨터에서 실행하는 에이전트 워크스페이스로 MagicLearn Pro 사용자에게 무료로 제공됩니다.

---

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 터미널에서 Claude Code와 Gemini CLI를 동시에 열고, 비서앱의 작은 기능 하나를 두 에이전트에게 같은 프롬프트로 맡긴 뒤 결과물을 나란히 비교해본다. 어떤 하네스가 대표님 코드베이스 컨텍스트를 더 잘 잡는지 감을 잡는 것이 목적.

**이번 주 1-2시간 (mid)**: McKay의 "에이전트 경마" 스크립트를 간단하게 흉내 내는 셸 스크립트를 작성한다. 예를 들어, 동일한 태스크를 Claude Code와 다른 에이전트에게 동시에 던지고, 결과를 `/tmp/agent_a.md`, `/tmp/agent_b.md`에 저장해 diff로 비교하는 자동화 루틴.

```bash
#!/bin/bash
PROMPT="$1"
# Claude Code 결과
echo "$PROMPT" | claude --output /tmp/agent_claude.md &
# Gemini CLI 결과 (설치 시)
echo "$PROMPT" | gemini --output /tmp/agent_gemini.md &
wait
diff /tmp/agent_claude.md /tmp/agent_gemini.md
```

**이번 달 실험 (macro)**: 비서앱 ERP의 새 기능 3개를 McKay 방식으로 개발한다 — 각 기능마다 두 에이전트를 경주시키고, 어느 쪽 결과물이 실제 프로덕션에 더 많이 채택되는지 트래킹. 측정 지표: 채택률(채택된 코드/전체 시도), 수정 횟수(채택 후 추가 편집 수), 개발 시간 단축률.

---

## 한국 솔로 운영자 맥락에서 주의

**멀티에이전트 토큰 비용이 빠르게 쌓인다.** McKay처럼 Claude Opus 4, Gemini 2.5 Pro, o3를 동시에 돌리면 하나의 태스크에 세 배의 API 비용이 발생합니다. 와당탕 비서앱·ERP처럼 반복 실행이 많은 내부 도구에 무분별하게 적용하면 월 비용이 급격히 증가합니다. 경마 전략은 새 기능 탐색이나 아키텍처 결정처럼 **"한 번 잘 결정하면 큰 가치"인 순간**에만 쓰는 것이 합리적입니다.

**영어권 교육 시장과 한국 시장의 구조 차이.** McKay의 MagicLearn 유료 모델은 25k 영어권 학습자 기반 위에서 작동합니다. 한국에서는 지피터스·조코딩 같은 플랫폼이 이미 커뮤니티를 선점하고 있어, chatbot-ui 같은 바이럴 오픈소스 → 유료 교육 깔때기를 복제하기 위해서는 한국어 특화 오픈소스 프로젝트나 옵시디언 플러그인 등 다른 허브가 필요합니다.

---

## 더 깊이 보려면

- [McKay Wrigley GitHub — chatbot-ui (33K stars)](https://github.com/mckaywrigley/chatbot-ui)
- [MagicLearn (Takeoff 리브랜드)](https://www.jointakeoff.com/)
- [MagicLearn 소개 블로그](https://www.jointakeoff.com/blog/magiclearn-takeoff)
- [McKay Wrigley 서브스택 — Claude Agent SDK 글](https://mckaywrigley.substack.com/p/claude-agent)
- [ARK Invest FYI 팟캐스트 ep.80 — McKay Wrigley 인터뷰 (2020 초기 비전)](https://www.ark-invest.com/podcast/ep80-mckay-wrigley)
- [McKay Twitter @mckaywrigley — 3 에이전트 경마 트윗](https://x.com/mckaywrigley/status/1937978348862578846)

---

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "어떤 에이전트가 제일 좋아요?"라는 질문이 2026년에도 여전히 의미없는 이유 — 태스크마다 다르고, 심지어 같은 사람도 3개월 만에 80/20 비율이 뒤집히기 때문.
- **숫자**: GitHub 스타 33,300개짜리 오픈소스 한 개가 25,000명 유료 교육 플랫폼의 씨앗이 됐다. 오픈소스 → 커뮤니티 신뢰 → 유료 전환의 속도.
- **삽질**: McKay는 Claude Code + Opus 4.5를 "세계 최고 AI 코딩 도구"라고 선언했다가, 3개월 뒤 "이제 코딩에서는 GPT를 80% 쓴다"고 공개적으로 정정했다. 모델 충성도를 갖는 게 아니라 결과로 계속 재보정하는 것이 그의 전략의 본질.
- **훅**: "에이전트를 선택하려고 시간을 쓰지 마세요. 다 경주시키고 이긴 놈 코드를 쓰세요."
