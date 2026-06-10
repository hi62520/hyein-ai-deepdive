---
date: 2026-06-11
category: 시스템방법론
subject: Ryan Singer — Shape Up, AI 시대에 다시 뜨는 베팅·사이클 방법론
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱/ERP의 다음 기능 하나를 "appetite: 이번 주 3시간" 으로 선언하고 Obsidian에 5줄 피치(문제/appetite/해결윤곽/rabbit hole/no-go) 작성
---

# Ryan Singer — Shape Up, AI 시대에 다시 뜨는 베팅·사이클 방법론

## 누구/무엇인가

Ryan Singer는 37signals(Basecamp)에서 17년을 일한 초기 멤버이자 Head of Strategy 출신입니다. 2019년에 팀의 제품 개발 방식을 공식화한 책 *Shape Up: Stop Running in Circles and Ship Work that Matters*를 무료로 공개하며 스크럼·스프린트의 대안을 제시했습니다. 현재는 독립 컨설턴트·Fractional CPO로 Felt Presence LLC를 운영하고 있습니다.

Shape Up은 요약하면 이렇습니다: "**sprint는 없다. 6주 사이클, appetite 기반 scope 설정, 베팅 테이블**"로 제품을 만든다는 운영 매뉴얼입니다. 스타트업과 대기업 모두 채택하며 꾸준히 퍼졌고, 2025–26년 AI 보조 코딩 붐이 터지면서 다시 한번 강력하게 주목받고 있습니다. Singer 자신이 Claude Code를 메인 코딩 도구로 사용하며 Shape Up의 shaping 단계를 AI로 자동화하는 실험을 공개 중입니다.

## 무엇이 특별한가

### 1. Estimate(추정)가 아니라 Appetite(허용 예산)로 시작한다

전통적 개발팀은 "이 기능 얼마나 걸려요?"라고 묻습니다. Shape Up은 반대입니다. **"이 문제에 우리는 얼마나 쓸 의향이 있나?"**가 출발점입니다.

> "Estimates start with a design and end with a number. Appetite starts with a number and ends with a design."  
> — Ryan Singer, *Shape Up*

6주짜리 appetite냐 2주짜리(소규모 배치)냐가 결정되면, 그 시간 안에 납입 가능한 형태로 솔루션을 디자인합니다. scope를 자르는 것이지 타임라인을 늘리는 것이 아닙니다. AI 시대에 이 원칙이 더 강력한 이유가 있습니다. LLM 보조 코딩은 구현 속도를 예측 불가능하게 만들기 때문에, 처음부터 추정을 포기하고 **고정 시간·가변 범위(Fixed Time, Variable Scope)** 로 움직이는 Shape Up이 오히려 더 자연스럽게 맞아떨어집니다.

### 2. 세 단계: Shape → Bet → Build (스프린트 없음)

- **Shape(형태 잡기)**: 실제 빌딩에 들어가기 전, 시니어 레벨이 '거칠게' 솔루션을 설계합니다. 요점은 "충분히 구체적이지만 구현자에게 판단을 남긴다"는 것. 도구는 **fat-marker sketch**(세세하게 못 그리는 두꺼운 펜 스케치)와 **breadboard**(UI 어포던스와 코드 어포던스를 와이어로 연결한 텍스트 회로도).
- **Bet(베팅)**: 2주 cool-down 중에 열리는 **betting table** 회의에서 다음 6주에 무엇을 만들지 베팅합니다. 백로그 없이 선택합니다.
- **Build(빌딩)**: 팀이 완전한 자율성으로 6주 내에 납입합니다. 끝나지 않으면 연장하지 않고 기본 취소합니다.(**circuit breaker** 규칙)

> "Six weeks is long enough to build something meaningful start-to-finish, and short enough that everyone can feel the deadline looming from the start."  
> — Ryan Singer, *Shape Up*

### 3. Hill Chart — 진행 상황을 '앎과 모름'으로 표시

전통적 번다운 차트는 "얼마나 남았나"를 보여줍니다. Shape Up의 **hill chart**는 다른 질문을 묻습니다: "아직 모르는 게 있나, 아니면 이제 다 알고 실행만 남았나?" 언덕의 오르막(uphill)은 불확실성 단계, 내리막(downhill)은 실행 단계입니다. 언덕에 올라가지 못하고 멈춘 항목은 문제가 있다는 신호입니다.

### 4. Circuit Breaker — 연장 없이 기본 취소

> "If a team doesn't successfully ship and deploy that piece of work within the bet, by default it's canceled."

이 원칙은 냉정해 보이지만, 실제로는 팀을 미래의 더 중요한 일로부터 묶어두는 '좀비 프로젝트'를 막습니다. 한 번 못 끝낸 기능은 다음 사이클에 다시 베팅할 수 있습니다. 완료하지 않는 것과 실패하는 것은 다릅니다.

### 5. 2025–26년: Ryan Singer가 Claude Code로 Shape Up 자동화 중

Singer는 최근 자신의 X(트위터) 계정(@rjs)에서 눈에 띄는 실험을 공개 중입니다:

- **"Claude Code is amazing during shaping"** (2025년 3월 트윗): 기존 코드베이스에서 도메인 언어 혼동 해결("우리가 `filter`라고 불러온 것이 코드에서는 `ParentFacet`이다"), 구현 seam 찾기 등에 Claude Code를 활용.
- **"I've been teaching Claude Code how to do technical shaping and breadboarding"** (2025년): 브레드보딩 스킬을 Claude에게 가르쳐 새 프로젝트에서 처음으로 one-shot breadboard를 생성하는 데 성공.
- **GitHub `rjs/shaping-skills`** 레포 공개: Claude Code Skills로 `/breadboarding`, `/shaping`, `/framing-doc`, `/kickoff-doc` 를 배포. 사용자는 `~/.claude/skills/` 에 심볼릭 링크를 걸면 그대로 활용 가능.

> "I'm even more fond of Claude Code after this great convo with the creator and lead PM. Refreshingly practical and down-to-earth. No AGI nonsense. (I've used Claude Code more than other tools for coding. Especially to learn how the existing system works.)"  
> — Ryan Singer, X(트위터) 2025년 5월 27일

Lenny Rachitsky 뉴스레터 팟캐스트에서는 Shape Up이 AI 시대에 다시 주목받는 이유를 직접 다뤘습니다. AI 코딩 도구가 '어떻게 짤까'를 대신 해결해주기 시작하면, 인간에게 남는 가장 고유한 작업이 바로 **'무엇을 베팅할 것인가'**를 결정하는 shaping 단계라는 것입니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**:  
비서앱 또는 ERP에서 "다음에 만들고 싶은 기능" 하나를 꺼내 Obsidian에 5줄 Shape Up 피치를 작성합니다.  
형식: `문제 / Appetite(예: 이번 주 3시간) / 솔루션 윤곽 / Rabbit hole(걸릴 수 있는 함정 1개) / No-go(이번에 안 하는 것 1개)`.  
이게 frontmatter `micro_action`과 동일합니다.

**이번 주 1-2시간 (mid)**:  
`rjs/shaping-skills` GitHub 레포를 클론해서 `/breadboarding` 스킬을 Claude Code에 설치합니다. 비서앱의 기존 기능 하나(예: 메모 등록 플로우)에 대해 `/breadboarding` 을 실행해보고 Places/UI Affordances/Code Affordances 표가 어떻게 나오는지 확인합니다.

```bash
# 설치 예시 (Claude Code ~/.claude/skills/ 디렉터리에 연결)
git clone https://github.com/rjs/shaping-skills.git
ln -s $(pwd)/shaping-skills/breadboarding ~/.claude/skills/breadboarding
ln -s $(pwd)/shaping-skills/shaping ~/.claude/skills/shaping
```

Claude Code에서 `/breadboarding` 명령으로 호출하면, 현재 코드베이스를 스캔해 어포던스 테이블을 자동 생성합니다.

**이번 달 실험 (macro)**:  
비서앱/ERP의 다음 릴리즈 사이클을 6주 Shape Up 사이클로 구조화합니다.
- Week 1–2: Claude Code + `/shaping` 스킬로 피치 2–3개 작성
- Week 3: Betting table (혼자라면 대표님 본인이 판단자 역할 + Claude에게 devil's advocate 역할 부여)
- Week 4–6: Build. 완료 못 하면 기본 취소, 다음 사이클에 재베팅
- 측정 지표: (1) 예상 사이클 내 납입률, (2) 기능당 출시까지 실제 경과일

## 한국 솔로 운영자 맥락에서 주의

**1. 혼자서는 betting table이 echo chamber가 됩니다.**  
Shape Up의 betting table은 CEO·CTO·시니어 개발자가 서로 견제하며 "이번 사이클에 뭘 베팅할지" 토론합니다. 솔로라면 자신이 유일한 결정자이므로, 매력적인 기능 쪽으로 계속 베팅이 쏠릴 위험이 있습니다. 해결책: Claude에게 "이 피치의 약점을 공격해줘"라는 역할을 주거나, 실제 사용자(비서앱 사용 고객)에게 피치 아이디어를 간략히 공유해 피드백을 받는 작은 루프를 만드세요.

**2. 6주는 솔로 사업가에게 길 수 있습니다.**  
Basecamp는 안정적인 수익이 있는 회사였기 때문에 6주 단위가 가능했습니다. 초기 비서앱/ERP처럼 빠른 반응이 필요한 제품은 **2주 사이클(소규모 배치)**를 먼저 적용해 body memory를 만든 뒤 6주로 확대하세요. Singer 자신도 "appetite은 2주와 6주 두 가지"라고 명시했습니다.

## 더 깊이 보려면

- [Shape Up 원문 (무료 웹버전)](https://basecamp.com/shapeup) — Ryan Singer, 2019
- [rjs/shaping-skills GitHub](https://github.com/rjs/shaping-skills) — Claude Code용 shaping·breadboarding 스킬 공개 레포
- [Lenny's Newsletter 에피소드: Ryan Singer](https://www.lennysnewsletter.com/p/shape-up-ryan-singer) — Lenny Rachitsky와의 대담
- [Shape Up이 2025년에 다시 뜨는 이유 (LinkedIn)](https://www.linkedin.com/pulse/shape-up-why-37signals-method-trending-again-2025-serge-bulaev-nxc4f)
- [Ryan Singer X(@rjs)](https://x.com/rjs) — Claude Code + Shape Up 실험 실시간 공개

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "스프린트를 쪼개고 또 쪼개도 뭔가 계속 늦어진다. 추정치가 틀리는 게 아니라, 추정 자체를 시작점으로 삼는 게 잘못이었다."
- **숫자**: 6주 사이클 + 2주 cool-down = 8주 단위 반복. Basecamp는 이 리듬으로 17년간 소규모 팀이 Basecamp·HEY·ONCE 같은 제품을 출시. Singer의 `rjs/shaping-skills` 레포는 2025년 공개 후 커뮤니티에서 즉시 포크·파생 레포(huntsyea/product-skills 등) 발생.
- **삽질**: Singer가 Basecamp 초창기에 백로그를 관리하려 했을 때, 항목이 수백 개 쌓이면서 정작 중요한 게 뭔지 알 수 없어졌다고 회고합니다. "백로그는 기억이 아니라 죄책감을 쌓는 공간"이라는 표현이 이를 반영합니다. 해결책이 '베팅 테이블'이었고, 베팅 후 선택받지 못한 항목은 자동 소멸합니다.
- **훅**: "오늘 만들 기능을 정한 다음, '이거 몇 시간 걸릴까?'라고 물으셨나요? Shape Up은 그 질문 순서가 틀렸다고 말합니다."
