---
date: 2026-07-09
category: 시스템방법론
subject: Maggie Appleton — 정렬이 구현보다 어렵다: 에이전트 팀의 병목 전환
tags: [AI탐구, deepdive]
starred: false
micro_action: 옵시디언에 "에이전트 합의 노트" 페이지를 만들어 오늘 Claude Code에 시킬 작업 목록을 에이전트별로 구분해 적고, 중복·충돌 항목을 체크한다
---

# Maggie Appleton — 정렬이 구현보다 어렵다: 에이전트 팀의 병목 전환

## 누구/무엇인가

Maggie Appleton은 GitHub Next의 Staff Research Engineer입니다. 디자이너 출신 엔지니어로, AI 시대의 인터페이스 패턴과 도구 설계를 탐구하는 독보적 목소리입니다. 그녀의 커리어는 독특합니다. Elicit(AI 리서치 도구 스타트업)에서 프로덕트 디자이너로 일하며 LLM 기반 인터페이스를 설계했고, 지금은 GitHub Next에서 "AI가 소프트웨어 엔지니어링을 어떻게 바꾸는가"를 연구하는 프로토타이프를 만들고 있습니다. 그녀를 유명하게 만든 건 개념을 시각 언어로 번역하는 능력입니다. Folk Interfaces, Squish Meets Structure, Barefoot Developers 같은 글은 AI 설계 커뮤니티에서 사실상 표준 참조문헌이 됐습니다. 2026년 초 그녀는 AI Engineer World's Fair에서 "One Developer, Two Dozen Agents, Zero Alignment"라는 제목의 강연을 발표했습니다. 이 강연은 에이전트 시대의 핵심 병목이 '구현 속도'에서 '팀 정렬'로 이동했다는 논증으로, 빌딩 커뮤니티에 큰 파장을 일으켰습니다.

## 무엇이 특별한가

**① 병목이 바뀌었다는 진단이 정확합니다**

Appleton이 제시한 핵심 통계는 날카롭습니다. 에이전트를 도입한 개발자는 하루 0.5개 기능을 구현하던 것에서 5개로 올라갔습니다. **10배 개인 생산성 향상**입니다. 그런데 팀은 더 힘들어졌습니다. "The bottleneck has shifted from implementation to alignment: the hard question is no longer *how* to build something, but *whether* it should be built at all." — 이제 어떻게 만들지가 아니라, 만들어야 하는지를 정하는 게 어려운 문제입니다. 누가 무엇을 만들고 있는지, 어떤 결정이 맥락 없이 병렬로 내려지고 있는지, 아무도 모르는 사이 "잠깐, 이거 누가 작업 중이야?" 슬랙 스레드가 폭증합니다.

**② 에이전트는 지금 모두 '싱글플레이어 게임'으로 설계돼 있습니다**

Appleton의 관찰은 간단하고 치명적입니다. Cursor, GitHub Copilot, Claude Code 등 현존하는 모든 코딩 에이전트는 개인의 생산성을 극대화하도록 설계됩니다. 그런데 소프트웨어 개발은 싱글플레이어 게임이 아닙니다. 팀으로 만듭니다. 개인은 10배 빨라졌는데, 팀 조율 도구는 아직 에이전트 이전 시대에 머물러 있습니다. 결과: 에이전트가 만든 PR은 리뷰어가 "이게 왜 필요해요?"를 물어야 이해가 됩니다. 맥락이 사라진 코드입니다.

**③ ACE 프로토타입 — 멀티플레이어 에이전트 작업 공간**

GitHub Next는 이 문제를 해결하기 위해 ACE(Agent Collaboration Environment)라는 연구 프로토타입을 만들었습니다. 구체 구성은 다음과 같습니다. 각 **Session**은 클라우드 microVM 위에서 돌아가는 멀티플레이어 채팅 공간입니다. 에이전트가 계획을 작성하면 팀 전체가 그 계획을 **실시간 커서로 공동 편집**할 수 있습니다. 팀이 합의한 뒤 "@ace do this"를 치면 그때서야 에이전트가 실행합니다. **팀 대시보드**는 아침에 미완 작업을 요약해주고, 팀원이 어제 무엇을 배포했는지 "팀 펄스"로 보여줍니다. ACE에서 만든 PR에는 세션 링크가 첨부되어, 다른 도구를 쓰는 팀원도 작업 맥락에 접근할 수 있습니다. 이 프로토타입은 수천 명 규모의 기술 미리보기를 앞두고 있습니다.

**④ Barefoot Developer — AI가 만드는 '맨발 개발자' 골든에이지**

Appleton의 또 다른 주요 테제는 "홈 쿠킹 소프트웨어"입니다. AI 코딩 도구의 발전으로 전통적 개발 경험 없이도 자신의 문제를 소프트웨어로 해결하는 사람들이 폭발적으로 늘어납니다. 그녀는 이들을 **barefoot developers**라고 부릅니다. 지역 커뮤니티에 깊이 뿌리박고, 주변 사람들의 문제를 정확히 알고, 그 문제를 LLM의 도움으로 해결하는 새로운 종류의 창작자입니다. Airtable, Notion 같은 기성 SaaS 위에서 워크플로우를 조립하던 사람들이 이제 자신만의 소프트웨어를 "집에서 요리"하게 됩니다. 이는 단순한 로우코드 혁명이 아니라 소프트웨어 창작의 민주화입니다.

**⑤ Squish-Structure 설계 스펙트럼 — 에이전트 UX의 핵심 긴장**

그녀가 2023년부터 전파한 개념이지만 2026년 에이전트 시대에 더 날카로워졌습니다. LLM의 본질은 "squish" — 유연하고 확률적입니다. 소프트웨어의 본질은 "structure" — 예측 가능하고 결정론적입니다. 이 긴장을 해소하지 않으면 인지 부하가 사용자에게 전가됩니다. 솔로 운영자 도구를 만드는 사람이라면 반드시 먼저 "이 기능이 squish해야 하는가, structure해야 하는가"를 결정해야 합니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 옵시디언에 "에이전트 합의 노트" 페이지를 만들어 오늘 Claude Code에 시킬 작업 목록을 에이전트별로 구분해 적고, 중복·충돌 항목을 체크한다. 솔로 운영자도 멀티 에이전트를 돌리면 '나 vs 나'의 정렬 문제가 생깁니다. 이 페이지가 그 해결책의 시작입니다.

**이번 주 1-2시간 (mid)**: 비서앱의 agent-push 엔드포인트 로그를 열어, 어제 실행된 자동화 각각이 "누가 왜 요청했는지"를 역추적할 수 있는지 점검합니다. ACE의 PR 링크 아이디어를 응용해 — 비서앱 ledger 메모에 트리거 출처(사용자 직접 / 스케줄 / 다른 에이전트)를 태깅하는 필드를 추가합니다.

```python
# ledger 메모 페이로드에 trigger_source 추가 예시
payload = {
    "content": f"📌 {task_name} 완료",
    "color": "green",
    "trigger_source": "schedule",  # "user" | "schedule" | "agent:deepdive"
    "session_ref": session_id       # ACE 세션 링크 개념 응용
}
```

**이번 달 실험 (macro)**: 비서앱 + ERP에서 에이전트별 '작업 펄스' 대시보드를 만들어봅니다. ACE의 팀 대시보드를 솔로 맥락으로 번역하면 "오늘 내 에이전트들이 무엇을 했는가"를 아침에 한 눈에 볼 수 있는 뷰입니다. 측정 지표: 에이전트 실행 수, 성공/실패율, 사람이 개입한 횟수. 이 숫자가 나오면 어디에서 정렬 비용이 발생하는지 보입니다.

## 한국 솔로 운영자 맥락에서 주의

**"팀 정렬" 문제가 이미 내부에 있습니다.** Appleton의 진단은 팀 단위 이야기처럼 보이지만, 솔로 운영자가 여러 에이전트를 동시에 돌리면 본인 내부에서 같은 문제가 발생합니다. 어제 deepdive 에이전트가 정리한 내용과 오늘 ERP 에이전트가 만든 코드가 서로 모순될 때 — 그게 솔로 운영자의 "Slack 스레드"입니다. ACE를 그대로 복사할 순 없지만, "먼저 계획을 합의한 뒤 실행"이라는 원칙은 지금 바로 적용할 수 있습니다.

**"Barefoot Developer" 자부심과 함정.** 와당탕/느린호밀 모델은 Appleton이 말한 barefoot developer의 한국형 선행 사례입니다. 다만 그녀의 경고도 함께 기억해야 합니다. 기성 SaaS보다 훨씬 많은 창작 자유를 갖지만, 그만큼 유지보수 책임도 혼자 집니다. "home-cooked"인 만큼, 주방이 더러워지면 나 혼자 치워야 합니다.

## 더 깊이 보려면

- [One Developer, Two Dozen Agents, Zero Alignment — maggieappleton.com](https://maggieappleton.com/zero-alignment)
- [Collaborative AI Engineering (YouTube — AI Engineer 강연)](https://www.youtube.com/watch?v=ClWD8OEYgp8)
- [Home-Cooked Software and Barefoot Developers — maggieappleton.com](https://maggieappleton.com/home-cooked-software)
- [Squish Meets Structure — maggieappleton.com](https://maggieappleton.com/squish-structure)
- [GitHub Next talks: One Developer, Two Dozen Agents](https://githubnext.com/talks/one-developer-two-dozen-agents-zero-alignment/)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: 에이전트 덕분에 하루 기능 5개를 만들었는데, 다음 날 팀원이 "그거 왜 만들었어요?"를 물었을 때의 허탈함. 솔로라면: 두 달 전 에이전트가 만든 코드를 내가 리뷰하면서 "이게 왜 여기 있지?"를 스스로 물을 때.
- **숫자**: 에이전트 도입 후 개인 생산성 **10배**(하루 0.5 → 5 기능). 그런데 팀 조율 비용은 측정 안 됨.
- **삽질**: ACE 프로토타입은 처음에 에이전트가 "즉시 실행"하도록 설계됐습니다. 테스트 중 팀이 "잠깐, 우리 이거 합의한 적 없는데?"를 반복하면서 "계획 먼저 편집, 승인 후 실행" 흐름으로 바뀌었습니다. 빠른 실행이 오히려 정렬 비용을 키웠습니다.
- **훅**: "AI 에이전트 덕분에 개발은 10배 빨라졌습니다. 그런데 왜 팀은 더 바빠졌을까요? 병목이 코드에서 대화로 이동했기 때문입니다."
