---
date: 2026-11-12
category: 시스템방법론
subject: Maggie Appleton — 구현은 에이전트에게, 판단은 나에게
tags: [AI탐구, deepdive]
starred: false
micro_action: 오늘 에이전트에게 맡긴 작업 1건에서 "내가 기대한 것 vs 실제로 한 것" 메모 1줄 남기기 (Capability Gaslighting 로그 시작)
---

# Maggie Appleton — 구현은 에이전트에게, 판단은 나에게

## 누구/무엇인가

Maggie Appleton은 디자이너, 인류학자, 그리고 스스로를 "mediocre developer"라고 부르는 GitHub Next 스태프 리서치 엔지니어입니다. 2025년 10월에 GitHub Next에 합류하기 전, 그녀는 AI 추론 도구 스타트업 Elicit의 첫 디자이너로 일했으며 LLM UI 패턴, 디지털 가든, '생각을 위한 도구(tools for thought)' 주제로 개발자 커뮤니티에서 오랫동안 영향력을 가져왔습니다. GitHub Next는 소프트웨어 엔지니어가 AI와 협업하는 방식의 미래를 연구하는 팀으로, 그녀는 그곳에서 프로토타입을 직접 만들고 그 경험을 글과 강연으로 공유합니다. 단순한 연구자가 아니라 "생각을 UI로 번역하는" 사람이라는 점에서 독보적입니다. 2026년 4월 AI Engineer World's Fair에서 발표한 "One Developer, Two Dozen Agents, Zero Alignment"는 에이전트 시대 협업 설계에 관한 가장 날카로운 진단으로 꼽힙니다.

## 무엇이 특별한가

**1. "AI는 구현을 해결했다, 생각은 아직 아니다"**

Appleton의 2026년 핵심 명제는 단순합니다: *"AI agents have solved implementation, not thinking."* 에이전트가 코드를 쓰고, UI를 만들고, PR을 올리는 속도는 이미 인간을 압도합니다. 그런데 그 사이에 "우리가 같은 걸 만들고 있나?"라는 정렬 문제가 아무도 모르게 커집니다. 과거의 병목이 "이걸 만들 수 있나?"였다면, 에이전트 시대의 병목은 "이걸 만들기로 합의했나?"로 옮겨갔습니다.

**2. Zero Alignment 문제 — 에이전트 24명과 일할 때 생기는 일**

그녀의 AI Engineer 발표 제목 그대로입니다: 개발자 1명이 에이전트 수십 개를 돌리면 무슨 일이 생길까요? 그녀는 세 가지 구체적인 현상을 꼽습니다. 첫째, 아무도 요청하지 않은 기능이 머지됩니다. 둘째, 에이전트들이 같은 파일을 동시에 수정해 머지 충돌이 쌓입니다. 셋째, 리뷰어가 맥락을 모르는 PR이 산더미처럼 쌓입니다. 에이전트는 코드베이스 안에 있는 정보는 읽을 수 있지만, 사업 맥락·제품 비전·조직의 역사는 코드베이스에 없기 때문에 발견할 수 없습니다. 현재의 에이전트 도구들은 본질적으로 '싱글 플레이어'이며, 팀 조정 레이어가 없다는 것이 그녀의 진단입니다.

**3. Capability Gaslighting — 에이전트가 나를 속이는 방식**

Appleton이 직접 명명한 개념입니다. 모델이 처음에 인상적인 결과를 보여주다가 얼마 지나지 않아 같은 작업에서 형편없이 실패하는 현상을 가리킵니다. 이 불일치가 개발자와 디자이너들로 하여금 AI가 무엇을 신뢰할 수 있게 할 수 있는지를 잘못 판단하게 만든다고 그녀는 주장합니다. Capability Gaslighting은 개인 생산성 뿐 아니라 팀 차원에서 더 위험합니다. "이 에이전트가 그 작업을 할 수 있다"는 잘못된 믿음이 팀 전체의 계획을 망가뜨리기 때문입니다. 솔로 운영자라면 자신이 기대한 것과 에이전트가 실제 한 것 사이의 갭을 직접 추적하고 명시화하는 것이 첫 번째 대응입니다.

**4. Jigs — 판단을 위한 개인 Figma**

그녀의 가장 실용적인 아이디어입니다. 'Jig'는 에이전트와 함께 직접 만드는 개인 프로토타이핑 도구입니다. 슬라이더, 색상 피커, 라이브 변수를 갖춘 미니 디자인 환경으로, Figma 없이 "이 버튼이 얼마나 커야 충분히 큰가", "이 스크롤은 얼마나 길어야 하는가"를 브라우저에서 직접 느끼며 판단할 수 있게 합니다. 그녀는 이 Jig의 코드를 직접 읽지 않습니다. 에이전트에게 넘기기 전에 상세한 스펙(에이전트가 작업을 어떻게 검증할 것인지 포함)을 작성하고, 결과물을 감각으로 판단합니다. 그녀의 표현: *"It's so much easier to have live variables — that would not have been possible before."*

**5. ACE와 Chopin — 협업 에이전트 UI의 프로토타입**

GitHub Next에서 그녀가 연구 중인 두 가지 프로토타입이 있습니다. ACE(Agent Collaboration Environment)는 팀원과 에이전트가 하나의 실시간 워크스페이스를 공유하는 멀티플레이어 코딩 환경입니다. Chopin은 팀의 계획 채팅을 배경에서 구조화된 플랜으로 변환하는 프로토타입으로, 에이전트가 사람을 기다리는 것이 아니라 사람에게 먼저 물어보는 방향의 인터페이스입니다. 이 두 프로젝트는 "에이전트가 텍스트박스를 초월한다"는 그녀의 명제를 UI 수준에서 구현하려는 시도입니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱에서 에이전트에게 맡긴 작업 1건을 돌아보고 "내가 기대한 것 vs 실제로 한 것" 메모 1줄 남기기. Capability Gaslighting 로그의 첫 항목입니다. 이것이 쌓이면 어떤 작업에서 에이전트를 신뢰할 수 있는지 패턴이 보이기 시작합니다.

**이번 주 1-2시간 (mid)**: Jig 하나를 만들어보세요. 비서앱 또는 ERP의 특정 UI 요소(예: 메모 입력창 크기, 버튼 위치, 색상 조합)를 에이전트에게 "슬라이더로 조절 가능한 HTML 프로토타입"으로 만들어 달라고 하고, 코드를 읽지 말고 느낌으로 판단해 보세요. 판단이 먼저고 코드는 나중입니다.

```
prompt 예시:
"이 비서앱 메모 UI의 프로토타입을 HTML+JS로 만들어줘.
폰트 크기, 줄 간격, 패딩을 슬라이더로 실시간 조절 가능하게.
코드 설명 없이 바로 실행되는 single file로.
검증 기준: 슬라이더 3개 모두 작동하고, 모바일 너비 375px에서도 깨지지 않을 것."
```

**이번 달 실험 (macro)**: "Zero Alignment 감사"를 ERP에 추가하세요. 에이전트가 완료한 작업 중 "원래 의도와 달라진 것" 목록을 월 1회 검토하는 습관입니다. 솔로 운영자라도 에이전트가 늘어날수록 나와 에이전트 사이의 정렬 비용이 쌓입니다. 측정 지표: "에이전트가 한 작업 중 내가 되돌린 비율". 이 숫자가 20%를 넘으면 스펙 작성 방식을 바꿀 신호입니다.

## 한국 솔로 운영자 맥락에서 주의

**"에이전트를 많이 쓸수록 좋다"는 착각**: Appleton의 연구는 에이전트 수와 품질이 반드시 비례하지 않는다는 것을 보여줍니다. 솔로 운영자는 팀보다 에이전트 정렬 비용이 낮다는 장점이 있지만, 에이전트 수가 늘면 자기 자신과의 정렬도 무너질 수 있습니다. "어제의 나와 오늘의 에이전트가 같은 방향을 보고 있나?"를 확인하는 루틴이 필요합니다.

**Jig를 사용자에게 직접 보여주는 함정**: 그녀의 Jig는 판단 도구이지 배포 산출물이 아닙니다. 한국 콘텐츠·강의 사업에서는 "에이전트로 빠르게 만든 것"을 미완성 상태로 고객에게 보여주는 순간 Capability Gaslighting의 반대 방향, 즉 과잉 기대 설정 함정에 빠질 수 있습니다.

## 더 깊이 보려면

- [One Developer, Two Dozen Agents, Zero Alignment (maggieappleton.com)](https://maggieappleton.com/zero-alignment)
- [AI Engineer World's Fair 발표 영상](https://www.youtube.com/embed/ClWD8OEYgp8)
- [Design Engineering with Maggie Appleton — Pragmatic Engineer 팟캐스트](https://newsletter.pragmaticengineer.com/p/design-engineering-with-maggie-appleton)
- [Agentic Coding Has Outgrown the Text Box — Tessl 팟캐스트](https://tessl.io/podcast/130)
- [GitHub Next: Making AI Multiplayer (AIE Europe 발표)](https://app.podcastguru.io/podcast/1620866569/episode/making-ai-multiplayer-with-maggie-appleton-from-github-next-aie-europe-b4c4fee4c02b9665558f82c447704552)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: 에이전트를 더 많이 써도 작업이 더 엉켜간다고 느끼는 순간 — Appleton의 연구는 그게 착각이 아니라 "Zero Alignment 문제"라는 실제 현상임을 보여줍니다.
- **숫자**: 개발자 1명, 에이전트 24개, 머지 충돌 무한 증가. "에이전트가 늘어날수록 팀 정렬 비용도 선형으로 늘어난다"는 패턴.
- **삽질**: 에이전트 도구를 도입했더니 오히려 PR 리뷰가 2배 늘었다는 팀들의 사례 — 에이전트는 구현 속도를 올리지만, 리뷰·정렬 비용은 자동으로 줄어들지 않는다.
- **훅**: "에이전트가 코드를 다 써줄 때, 당신은 무엇을 하고 있나요? — Maggie Appleton의 답: 여전히 노트에 스케치를 하고 있다."
