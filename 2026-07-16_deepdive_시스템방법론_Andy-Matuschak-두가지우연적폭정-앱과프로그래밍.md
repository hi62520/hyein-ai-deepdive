---
date: 2026-07-16
category: 시스템방법론
subject: Andy Matuschak — 앱과 프로그래밍, 두 가지 우연적 폭정에서 벗어나는 법
tags: [AI탐구, deepdive]
starred: false
micro_action: 옵시디언에서 오늘 읽은 글 1개를 원자 노트 1개로 변환 — 제목은 주장문(claim) 형태로, 본문은 5문장 이내로 작성하고 'evergreen' 태그 붙이기
---

# Andy Matuschak — 앱과 프로그래밍, 두 가지 우연적 폭정에서 벗어나는 법

## 누구인가

Andy Matuschak은 Apple에서 iOS SDK와 UIKit을 설계하고, Khan Academy에서 R&D를 이끈 후 2019년부터 독립 연구자로 전향했습니다. 자신의 Patreon 커뮤니티의 후원만으로 생계를 유지하며 "Tools for Thought(사고 도구)"라는 단 하나의 질문에 매달려왔습니다. 그의 공개 작업 노트(notes.andymatuschak.org)는 수천 개의 상호 연결된 에버그린 노트로 이루어져 있으며, "완성된 에세이"가 아닌 "사고 중인 실시간 두뇌"를 인터넷에 공개한 선례입니다. 2025년 말에는 Taylor Rogalski와 함께 **Pico**("인간 주의력을 위한 음악원")라는 스타트업을 공동 창업하며 준학문적 휴가(para-academic leave)를 선언했습니다. 현재 그는 독립 연구자, 에세이스트, 스타트업 공동창업자라는 세 정체성을 동시에 살고 있습니다.

## 무엇이 특별한가

### 1. "두 가지 우연적 폭정" — 2026년 3월 MIT 강연

2026년 3월 3일, MIT HCI 세미나에서 발표한 "Apps and programming: two accidental tyrannies"는 Matuschak이 최근 가장 명확하게 입장을 정리한 강연입니다. 그는 현대 소프트웨어가 우리를 두 가지 "우연히 만들어진 폭정" 아래 가뒀다고 주장합니다. 첫 번째 폭정은 **앱 모델** — 대규모 시장을 위해 설계된 one-size-fits-all 패키지에서 사용자는 개발자가 허락한 노브만 돌릴 수 있습니다. 두 번째 폭정은 **프로그래밍 자체** — 소프트웨어를 수정하려면 전문 성직자 계층(a specialist priesthood)을 거쳐야 하기 때문에 최종 사용자는 수동 소비자로 전락합니다. 흥미로운 점은, Matuschak이 이 두 폭정의 돌파구를 LLM 코딩 에이전트에서 찾는다는 것입니다. "2025년 말, 내 디자이너 협업자들은 새로운 인터페이스 아이디어를 일상적으로 프로토타이핑하고 몇 주에 걸쳐 반복 작업을 이어갔다"고 직접 증언했습니다. 비프로그래머가 자신의 도구를 직접 빚을 수 있는 시대가 열리고 있다는 것이죠.

### 2. Memory Machines — LLM의 '감각' 부재를 숫자로 증명

2026년 4월, Matuschak은 Ozzie Kirkby와 공동으로 **Memory Machines** 연구를 발표했습니다. 핵심 질문은 "LLM이 독자의 하이라이트에서 지속 가능한 플래시카드를 만들 수 있는가?"였습니다. 93개 출처에서 약 1,500개의 라벨링된 플래시카드 데이터셋을 구축하고 최신 LLM들을 평가한 결과, 최고 성능 모델(GPT-5.2)조차 **36%의 카드가 사용 불가능했습니다.** 실패 원인은 환각(hallucination)이 아니었습니다. "LLMs lack the 'taste' required to project whether a flashcard will be timeless enough to go into a deck." — LLM은 플래시카드가 장기 복습 사이클에서 살아남을 만큼 '시대를 초월'할지 판단하는 감각 자체가 없다는 결론입니다. 스스로 "베이 에어리어에서 스페이스드 리피티션을 다양하고 창의적인 방식으로 쓰는 사람 100명 이상을 안다"고 밝힌 그가 LLM 자동화에 회의적인 이유를 데이터로 보여준 것입니다.

### 3. Obsidian + LLM = 말라블 소프트웨어의 첫 번째 글림프스

2025년 3월, Matuschak은 Patreon 후원자들에게 "A startling glimpse of malleable software: LLM-generated Obsidian plugins"라는 서한을 보냈습니다. Taylor Rogalski가 LLM 에이전트에게 Obsidian 플러그인 기능을 end-to-end로 구축하게 하는 실험을 진행했고, 그 결과 **'Trough'** — 플러그인을 생성하는 Obsidian 플러그인 — 이 탄생했습니다. Matuschak이 전통적 엔지니어링 방식으로 수일을 소요한 기능을, 비프로그래머인 Rogalski가 LLM을 통해 몇 시간 만에 구현했습니다. 이 경험이 2026년 MIT 강연의 핵심 논지로 이어졌습니다. 지금 대표님이 Claude Code로 비서앱과 ERP를 직접 개발하는 것은 — Matuschak의 프레임으로 보면 — 두 가지 폭정에서 동시에 탈출하는 행위입니다.

### 4. Blips와 Pico — 프로그래머블 주의력이라는 새로운 실험

Pico는 단순한 스타트업이 아닙니다. Matuschak과 Rogalski는 **"Blips"** 라는 시간 조정된 주의력 개입 단위를 수년간 실험해왔습니다. 스페이스드 리피티션이 "기억을 위한 시간 조정"이라면, Blips는 "창의 작업(읽기, 사고, 표현, 문제 해결)을 위한 시간 조정"을 목표로 합니다. Matuschak은 소셜 미디어가 주의력을 파괴하는 메커니즘을 직접 언급했습니다 — "X/YouTube를 48시간 전에 봤으면 몇 분 만에 산만해지지만, 스크롤 없이 지냈으면 한 시간씩 집중할 수 있다"고요. Pico는 이 문제를 기술적으로 해결하려는 시도입니다. "인간 주의력을 위한 음악원(conservatory for human attention)"이라는 슬로건이 그 야심을 담습니다.

### 5. "The Primer를 퇴마하라" — AI 시대 교육환상 비판

Matuschak의 2024년 에세이 "Exorcising us of the Primer"는 Neal Stephenson의 SF 소설 속 마법 같은 학습 도구 "The Young Lady's Illustrated Primer"에 대한 교육계의 환상을 정면으로 비판합니다. 그는 Primer 같은 만능 AI 튜터가 세 가지 근본 결함을 갖는다고 지적합니다: 학습자가 선택하지 않은 가치관을 주입하는 "숨겨진 의제", 진짜 인간 관계 없이는 채울 수 없는 "연결의 공백", 그리고 발견 학습이 작업 기억 한계를 무시한다는 "인지과학 부재". AI 튜터가 모든 것을 대답해주는 환경이 진짜 학습을 방해한다는 이 주장은, 2026년 현재 AI 교육 도구가 폭발적으로 늘어나는 상황에서 더욱 날카롭게 들립니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 옵시디언에서 오늘 읽은 글 1개를 원자 노트 1개로 변환하세요. 제목은 반드시 주장문(claim) 형태로 — "Andy Matuschak은 도구를 연구한다"가 아니라 "LLM은 아직 플래시카드의 감각이 없다"처럼. 본문은 5문장 이내, 'evergreen' 태그를 붙이세요. Matuschak이 7년 동안 쌓아온 에버그린 노트 시스템의 첫 번째 벽돌이 됩니다.

**이번 주 1-2시간 (mid)**: 비서앱이나 ERP의 기능 명세 중 하나를 "Doing-centric"으로 재설계해보세요. 현재 "기능 목록 → 클릭" 구조 대신, "사용자가 무엇을 하고 싶은지"를 먼저 쓰고 그 흐름 안에 텍스트 설명을 최소화하는 방식입니다. Claude Code로 Obsidian 플러그인 하나를 직접 생성하는 시도도 좋습니다 — Trough 실험의 재현입니다. 코드 스니펫:

```javascript
// 옵시디언 커맨드 팔레트에 'Create Evergreen Note' 추가하는 가장 단순한 플러그인 구조
module.exports = class EvergreenPlugin extends Plugin {
  async onload() {
    this.addCommand({
      id: 'create-evergreen',
      name: 'Create Evergreen Note',
      callback: () => {
        const title = prompt('주장문(claim) 형태의 제목:');
        if (title) this.app.vault.create(`${title}.md`,
          `---\ntags: [evergreen]\n---\n\n`);
      }
    });
  }
};
```

**이번 달 실험 (macro)**: Blips 개념을 와당탕 업무 루틴에 이식해보세요. 매일 아침 비서앱이 "오늘 다시 볼 주제 3개"를 자동으로 뱉는 구조 — 단 스페이스드 리피티션 알고리즘(SM-2)이 아니라, "마지막으로 실행한 날 + 진행률"을 기준으로 최우선 업무를 자동 추천하는 것입니다. 측정 지표: 한 달 후 "한 번 보고 잊어버린 아이디어"의 수가 줄었는지.

## 한국 솔로 운영자 맥락에서 주의

**속도의 함정**: Matuschak이 Memory Machines에서 보여준 것처럼, LLM이 자동으로 생성한 지식 카드의 36%는 실제 복습에서 살아남지 못합니다. Claude에게 "오늘 배운 내용 정리해줘"를 맡기면 빠르게 많은 노트를 생성할 수 있지만, 그 노트들이 6개월 후에도 살아있을지는 별개의 문제입니다. LLM은 속도를 줍니다. 감각(taste)은 대표님이 직접 가져야 합니다.

**규모의 환상**: Pico와 Blips는 수년간의 개인 실험에서 나온 시스템입니다. Matuschak은 Patreon 커뮤니티 100-200명의 후원을 받으며 6-7년을 매달려서 이 개념에 도달했습니다. 한국 솔로 운영자 입장에서 "주의력 관리 시스템 구축"은 한 달 안에 완성되는 프로젝트가 아닙니다. 작은 습관 하나를 먼저 이식하고 측정하는 방식이 현실적입니다.

## 더 깊이 보려면

- [Apps and programming: two accidental tyrannies (MIT 강연, 2026-03-03)](https://andymatuschak.org/tat/)
- [MIT 강연 유튜브 영상](https://www.youtube.com/watch?v=ycyCGCtScdc)
- [Memory Machines 연구 보고서](https://memory-machines.com/report)
- [What's worth learning if we have AGI?](https://andymatuschak.org/worth-learning-agi/)
- [Exorcising us of the Primer](https://andymatuschak.org/primer/)
- [Why books don't work](https://andymatuschak.org/books/)
- [Dwarkesh Patel 팟캐스트 — 양자역학 교과서 함께 읽기 (2025년 8월)](https://www.dwarkesh.com/p/andy-matuschak)
- [Andy Matuschak 공개 작업 노트](https://notes.andymatuschak.org/)
- [Augmenting Attention 대담 (YouTube)](https://www.youtube.com/watch?v=VRGueEexbzo)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "책을 읽었는데 다음 날 아무것도 기억나지 않는다" — 이건 의지력 문제가 아니라 미디어 설계 문제입니다. 교과서는 원래 기억을 위해 설계된 게 아닙니다.
- **숫자**: LLM 최고 모델(GPT-5.2)이 자동 생성한 플래시카드 중 **36%는 장기 복습에서 살아남지 못한다** — Memory Machines 2026년 4월 연구. "AI가 다 해준다"는 환상을 데이터로 부수는 숫자.
- **삽질**: Matuschak은 수년간 노트 앱, 스페이스드 리피티션 도구, 상호작용 교과서를 만들었지만 — "사람들이 도구를 쓰지 않는 게 아니라, 도구가 실제 학습을 만들지 못한다"는 사실을 계속 발견했습니다. 솔루션이 아닌 근본 질문으로 돌아가는 게 7년 반복 패턴.
- **훅**: "GPT-4가 나왔을 때 저는 솔직히 아직 그 변화한 세계를 소화하지 못했다고 고백했습니다. 2026년 지금 대부분의 AI 사용자가 그 상태입니다 — 도구는 쓰는데, 정작 뭘 배우고 기억해야 할지는 모릅니다."
