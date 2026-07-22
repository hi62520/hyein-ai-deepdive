---
date: 2026-07-23
category: 시스템방법론
subject: Steph Ango — 에이전트에게 볼트를 가르쳐라 (obsidian-skills)
tags: [AI탐구, deepdive]
starred: false
micro_action: 옵시디언 볼트 루트에 `npx skills add https://github.com/kepano/obsidian-skills` 한 줄 실행해서 obsidian-markdown 스킬 설치, Claude Code로 [[wikilink]] 하나 테스트 생성해보기
---

# Steph Ango — 에이전트에게 볼트를 가르쳐라

## 누구/무엇인가

Steph Ango(깃허브 핸들 `kepano`)는 Obsidian의 CEO입니다. 생물학과 산업디자인을 전공했고, 디자이너·작가·도구 제작자로 활동하다 전 사용자에서 CEO로 올라선 독특한 이력을 가지고 있습니다. 7명짜리 팀이 수백만 명이 쓰는 소프트웨어를 만든다는 사실이 그를 솔로프레너 커뮤니티에서 특별하게 만듭니다. 그는 "File over App" 철학으로 이미 2026년 5월 딥다이브에서 다뤘지만, 2026년 1월 조용히 GitHub에 올린 `kepano/obsidian-skills` 리포지토리가 6월을 기점으로 폭발적인 반향을 일으키며 전혀 다른 이야기의 주인공이 됐습니다. 출시 초기 3개월 만에 5,247 스타를 받았고, 6월 이후 37,000 스타를 넘어섰습니다. 주요 프로덕티비티 앱 CEO가 직접 자기 앱을 위한 AI Agent Skills를 공식 제작·배포한 건 역사상 최초 사례입니다.

obsidian-skills는 다섯 개의 Agent Skills 파일로 구성된 오픈소스(MIT 라이선스) 패키지입니다. Claude Code, Codex, Open Code 등 Agent Skills 명세를 지원하는 에이전트라면 어디서든 사용 가능합니다. 설치는 한 줄입니다: `npx skills add https://github.com/kepano/obsidian-skills`. 가격은 $0입니다.

## 무엇이 특별한가

### 1. "File over App" 철학의 자연스러운 연장

File over App은 "앱이 사라져도 파일은 남는다"는 주장입니다. 2023년 Steph Ango가 쓴 그 에세이의 핵심은 데이터를 앱에 가두지 말라는 것이었습니다. 2026년의 obsidian-skills는 그 철학의 다음 챕터입니다. 질문은 이겁니다: "AI 에이전트가 등장했을 때, 파일 우선주의자는 어떻게 반응해야 하는가?" 많은 앱들이 내린 답은 "볼트 데이터를 AI 클라우드로 가져오자"였습니다. Steph Ango의 답은 정반대입니다 — "AI를 파일의 세계로 데려오자." 볼트를 이동시키는 대신, 에이전트가 볼트의 언어를 배우게 만드는 것입니다.

그의 철학을 한 문장으로 표현하면: *"Use AI on the files, not instead of the files."* (AI로 파일 위에서 일하라, 파일 대신 AI로 가지 마라.) 에이전트는 당신이 무엇을 믿는지, 어떤 노트가 어떤 의미를 갖는지 대신 결정해서는 안 된다는 것이 그의 입장입니다. 에이전트는 당신의 판단을 실행하는 손이어야지, 당신의 생각을 대체하는 뇌가 돼선 안 된다고 봅니다.

### 2. 다섯 개 스킬이 해결하는 핵심 문제

obsidian-skills가 없을 때 Claude는 Obsidian 파일을 "읽을" 수는 있지만, Obsidian 방식으로 "쓰지" 못했습니다. 표준 Markdown을 생성하기 때문에 `[[wikilink]]`를 `[wikilink](wikilink.md)`로 잘못 작성하고, Frontmatter YAML 문법을 틀리고, Bases 파일의 뷰·필터 구조를 모르고, Canvas 노드 연결 방식을 이해하지 못합니다. 각 스킬은 Claude에게 해당 형식을 명시적으로 가르칩니다:

- **obsidian-markdown**: `[[wikilink]]`, 임베드(`![[파일명]]`), 콜아웃 박스, YAML 프로퍼티 등 Obsidian Flavored Markdown 전체 문법 교육. 커뮤니티 리뷰에서 "이 스킬 하나만 설치해도 노트들이 분리된 파일 더미에서 탐색 가능한 지식 네트워크로 바뀐다"는 평가가 나왔습니다.
- **obsidian-bases**: Obsidian Bases 파일(`.base`)의 뷰, 필터, 수식, 요약 기능 교육. 에이전트가 데이터베이스형 노트를 생성하고 수정할 수 있게 됩니다.
- **json-canvas**: Canvas 파일(`.canvas`)의 노드, 엣지, 연결 구조 교육. 시각적 지식 지도를 에이전트가 작성하게 됩니다.
- **obsidian-cli**: 커맨드라인으로 볼트와 상호작용하는 방법 교육. 플러그인·테마 개발 자동화에 활용됩니다.
- **defuddle**: 웹 페이지에서 클린 마크다운을 추출하는 CLI 툴 교육. WebFetch 대신 사용해서 토큰을 절약합니다. (`defuddle parse <url> --md` 한 줄로 광고·내비게이션 없이 본문만 추출.)

### 3. 37,000 스타가 말하는 것

출시 초기 3개월(1~3월) 동안 5,247 스타를 모았고, 6월부터 폭발해 37,000 스타를 돌파했습니다. 이 속도는 "잠재 수요가 이미 있었다"는 신호입니다. 수백만 명의 Obsidian 사용자들이 Claude와 자신의 볼트를 연결하고 싶었지만, 에이전트가 볼트 문법을 망가뜨리는 문제를 해결할 공식 방법이 없었습니다. CEO가 직접 나서서 그 다리를 놓자 커뮤니티가 움직인 것입니다.

또 하나 주목할 점: Agent Skills 명세(agentskills.io)를 Obsidian 측이 공식 채택했다는 신호이기도 합니다. 이 명세는 Claude Code, OpenAI Codex, Open Code 어디서나 같은 스킬 파일을 쓸 수 있는 공통 포맷입니다. 특정 AI 회사에 종속되지 않는 "파일 우선주의"의 AI 버전입니다.

### 4. 7명 팀이 만드는 생태계 — 솔로프레너십의 레퍼런스

2026년 5월 Cortex 팟캐스트 #179에서 Steph Ango는 7명의 팀이 수백만 명에게 소프트웨어를 제공하는 방식을 설명했습니다. 회의 없이 일하고, 커뮤니티가 플러그인·테마·워크플로우·실천법을 만들어 확장하며, 핵심 팀은 철학적 일관성을 유지하는 역할에 집중합니다. obsidian-skills도 마찬가지입니다 — 5개 SKILL.md 파일로 구성된 리포지토리이지만, 그 위에 커뮤니티가 30가지 워크플로우와 수십 개의 가이드를 만들어냈습니다. "적게 만들되, 본질을 만들면 커뮤니티가 나머지를 완성한다"는 전략입니다.

### 5. "AI 제어 취소"가 아닌 "AI 역할 제한"

Obsidian의 AI 전략은 반(反)-AI가 아닙니다. "AI 인수 방지(anti-takeover)"입니다. Steph Ango는 Obsidian의 Anthropic 협업을 공식 Claude 연동으로 선택한 이유를 두 가지로 설명합니다: 1) Claude Code는 파일을 네이티브로 읽고, 2) Anthropic의 프라이버시 입장이 Obsidian의 로컬 퍼스트 철학과 정렬됩니다. 데이터가 사용자 기기 밖으로 나가지 않는 방식으로 AI를 볼트에 연결할 수 있다는 것이 그의 선택 근거입니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 옵시디언 볼트 루트에서 아래 한 줄을 실행하고 Claude Code에서 테스트해보세요:
```bash
npx skills add https://github.com/kepano/obsidian-skills
```
설치 후 Claude Code에 이렇게 지시해보세요: "내 볼트의 오늘 deep dive 노트에 [[와당탕연구소]] 와 [[느린호밀]] wikilink를 추가해줘." 이전과 달리 `[[이중괄호]]` 형식으로 정확하게 작성하는 것을 확인하면 됩니다. frontmatter 필드도 마찬가지로 정확하게 생성됩니다.

**이번 주 1-2시간 (mid)**: obsidian-skills를 비서앱 개발 워크플로우에 통합해보세요. Claude Code에게 다음과 같이 지시합니다: "비서앱 ERP 개발 노트를 Obsidian Bases 파일로 만들어줘. 기능 목록, 상태(미완료/진행중/완료), 우선순위를 필터링할 수 있게." Bases 스킬이 없을 때는 이 요청이 오류 투성이 파일을 만들었지만, 스킬이 있으면 Obsidian에서 즉시 작동하는 `.base` 파일이 생성됩니다.

```bash
# Claude Code에 보낼 지시 예시
"와당탕 ERP 기능 목록을 Obsidian Bases 파일로 만들어줘.
컬럼: 기능명 | 카테고리 | 상태 | 마감일 | 담당(대표님)
필터: 상태 = 진행중 인 것만 기본 표시
파일명: ERP-기능-현황.base"
```

**이번 달 실험 (macro)**: defuddle 스킬을 활용해 '웹 아티클 → 옵시디언 노트' 자동 파이프라인을 구성해보세요. 대표님이 아티클 URL을 Claude Code에 던지면, defuddle로 클린 마크다운 추출 → Obsidian 방식으로 frontmatter 추가 → 볼트의 적절한 폴더에 저장하는 워크플로우입니다. 30일간 운영하고 "직접 노트 작성 시간 대비 자동 수집 노트 수" 비율을 측정합니다. Steph Ango의 말대로 당신이 노트의 큐레이터로 역할이 바뀌는 경험을 하게 됩니다.

## 한국 솔로 운영자 맥락에서 주의

**Obsidian-skills는 '에이전트가 볼트를 이해하는 것'이지 '에이전트가 지식을 대신 구성하는 것'이 아닙니다.** Steph Ango가 명시적으로 선을 긋는 것이 이 지점입니다: "AI가 당신이 무엇을 믿는지, 어떤 노트가 어떤 의미를 갖는지 결정해서는 안 된다." 스킬 설치 후 "내 볼트를 자동으로 정리해줘"라고 시키는 것은 이 철학에 어긋납니다. 대신 "이 노트에 관련 링크를 추가해줘", "이 URL의 내용을 내 폴더 구조에 맞게 저장해줘" 같이 실행 지시에 집중하는 것이 맞습니다. 생각의 구조는 여전히 대표님이 만들어야 합니다.

**Bases·Canvas 스킬은 아직 실험적입니다.** obsidian-markdown은 안정적이지만, Bases와 Canvas는 Obsidian이 비교적 최근 추가한 기능이라 에이전트가 생성한 파일에 오류가 있을 수 있습니다. 중요한 데이터를 다룰 때는 생성된 파일을 Obsidian에서 직접 열어 확인하는 과정을 거치는 것을 권장합니다.

## 더 깊이 보려면

- [kepano/obsidian-skills — GitHub](https://github.com/kepano/obsidian-skills)
- [Cortex #179: The Philosophy of Obsidian, with CEO Steph Ango — Relay FM](https://relay.fm/cortex/179)
- [Inside Steph Ango's Obsidian Workflow: Bottom-Up Digital Thinking — LavX](https://news.lavx.hu/article/inside-steph-ango-s-obsidian-workflow-a-bottom-up-approach-to-digital-thinking)
- [Obsidian Skills Review 2026 — VibeCoding.app](https://vibecoding.app/blog/obsidian-skills-review)
- [obsidian-skills: Help Claude Code Read and Write Obsidian Notes — Tecmint](https://www.tecmint.com/obsidian-skills-claude-code-linux/)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "Claude Code에 '내 옵시디언 노트 수정해줘' 했더니 wikilink를 전부 일반 Markdown 링크로 바꿔버렸다." 옵시디언 유저 99%가 겪는 공통 고통. Steph Ango가 이 문제를 해결하러 직접 나선 이유입니다.
- **숫자**: 37,000 GitHub 스타 (6개월 만). 7명 팀 × 수백만 사용자 = 1인당 수십만 유저 지원. obsidian-skills: 5개 파일, $0, MIT 라이선스. "첫 번째 주요 프로덕티비티 앱 CEO가 직접 만든 공식 AI Agent Skills."
- **삽질**: obsidian-skills 없이 Claude에게 Canvas 파일을 만들게 하면 JSON 구조가 틀려 Obsidian에서 열리지 않는 파일이 생성됩니다. 또는 Bases 파일을 요청했더니 평범한 .md 테이블로 만드는 경우. 스킬 하나로 이 오류들이 사라집니다.
- **훅**: "AI가 내 노트를 '읽는' 것과 AI가 내 노트를 '이해하고 쓰는' 것은 다릅니다. 옵시디언 CEO가 직접 그 차이를 해결하는 파일 5개를 만들었습니다. 지금부터 30분이면 여러분 볼트에 적용할 수 있습니다."
