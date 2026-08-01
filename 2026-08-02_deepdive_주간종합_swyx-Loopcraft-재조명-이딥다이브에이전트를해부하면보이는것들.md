---
date: 2026-08-02
category: 주간종합
subject: swyx Loopcraft 재조명 — 이 딥다이브 에이전트를 해부하면 보이는 것들
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱에서 가장 반복되는 판단 1개를 골라 "Inner Loop 명세서"를 노션/옵시디언에 3줄로 적는다 (트리거 조건 / 실행 동작 / 검증 기준)
---

# swyx Loopcraft 재조명 — 이 딥다이브 에이전트를 해부하면 보이는 것들

## 이 재조명이 다루는 각도

지난 화요일(07-29) 딥다이브에서 swyx의 Loopcraft 개념 — "루프를 쌓는 자가 에이전트 시대를 지배한다" — 를 살펴봤습니다. 오늘은 그 이론을 추상으로 두지 않고, 대표님이 매일 아침 읽고 있는 **이 딥다이브 시스템 자체를 해부**하는 방식으로 재조명합니다. 가장 이해하기 쉬운 루프 교과서는 이미 대표님 손 안에 있습니다.

---

## 누구/무엇인가 (이 재조명의 맥락)

swyx(Shawn Wang)와 Latent Space가 AIEWF 2026 개막 키노트에서 선언한 테제: *"From chat, to tools, to goals — we're all about cron jobs and loops."* 채팅 → 도구 → 목표로 진화한 AI 사용 방식은 결국 **루프**로 수렴합니다. 루프를 설계하는 능력이 다음 10년 솔로 운영자의 핵심 레버가 된다는 것이 swyx의 진단입니다. 그런데 루프 설계를 배우는 가장 빠른 방법은 책이 아니라, 이미 작동하는 루프를 뜯어보는 것입니다. 지금 대표님 앞에는 매일 아침 7시에 스스로 깨어나 글을 쓰고, 커밋하고, 텔레그램을 보내는 루프가 있습니다. 이것을 해부합니다.

---

## 무엇이 특별한가 — 딥다이브 루프 해부

### 0. 루프가 이미 시대정신이다 — 세 가지 인용

재조명을 시작하기 전에, 2026년 6-7월 AI 엔지니어링 세계를 관통한 세 문장을 먼저 꺼냅니다.

**Peter Steinberger** (2026년 6월 7일 트윗, Latent Space Loopcraft 포스트의 도화선):
> *"Here's your monthly reminder that you shouldn't be prompting coding agents anymore. You should be designing loops that prompt your agents."*
(번역: "이달의 알림: 이제 에이전트에게 프롬프트를 보내는 걸 그만둬야 합니다. 당신이 할 일은 에이전트에게 프롬프트를 보내는 루프를 설계하는 것입니다.")

**Boris Cherny** (Claude Code 총괄, Anthropic):
> *"I don't prompt Claude anymore. I have loops running. They're the ones prompting Claude and figuring out what to do. My job is to write loops."*
(번역: "저는 더 이상 Claude에게 프롬프트를 보내지 않습니다. 루프가 돌고 있고, 루프가 Claude에게 프롬프트를 보냅니다. 제 일은 루프를 짜는 것입니다.")

**Karpathy** (No Priors 팟캐스트 인터뷰):
> *"To get the most out of the tools that have become available now, you have to remove yourself as the bottleneck. You cannot be there to prompt the next thing. You need to take yourself outside the loop."*
(번역: "지금 가용한 도구를 최대한 활용하려면, 당신 자신이 병목이 되어서는 안 됩니다. 다음 프롬프트를 보내는 사람이 당신이어서는 안 됩니다. 당신은 루프 바깥에 있어야 합니다.")

그리고 swyx의 AIEWF 2026 키노트 핵심 선언:
> *"One might argue the entire game of the next century is to be able to stack loops as effectively as possible."*
(번역: "어쩌면 다음 세기의 전체 게임은 루프를 얼마나 효과적으로 쌓느냐의 문제일지도 모릅니다.")

이 네 문장이 공통으로 가리키는 것: **프롬프트를 보내는 사람이 아니라, 루프를 설계하는 사람이 다음 시대를 지배한다.**

### 1. 이 시스템은 3개 레이어의 루프 스택이다

swyx가 "Stacking Loops"라고 부르는 구조를 이 시스템에서 그대로 찾을 수 있습니다.

**Inner Loop (실행 루프)**: 가장 안쪽. 오늘의 카테고리(일요일=주간종합)를 판단하고, WATCHLIST와 기존 파일을 대조해 후보를 선정하고, 웹 리서치를 수행하고, 1000-1500단어 마크다운을 작성합니다. 이 루프는 매일 반복되며, 각 실행은 독립적이고 완결적입니다.

**Outer Loop (관찰 루프)**: 중간 레이어. WATCHLIST.md가 이 역할을 합니다. 매일의 Inner Loop 실행 결과(어떤 인물을 다뤘는가)가 축적되고, Outer Loop는 30일 창문 안에서 중복을 필터링하며 전체 포트폴리오의 균형을 봅니다. 지금까지 다룬 100개+ 파일 목록이 곧 Outer Loop의 상태(state)입니다.

**Meta Loop (전략 루프)**: 가장 바깥. CLAUDE.md 같은 시스템 프롬프트에 담긴 규칙 자체입니다. 어떤 요일에 어떤 카테고리를 다루는가, 어떤 형식으로 쓰는가, 어떤 지표(단어 수, 텔레그램 OK, ledger push)를 성공 기준으로 삼는가. 이 레이어는 매일 바뀌지 않지만, 대표님이 주기적으로 개입해 업데이트하면 Inner Loop 전체가 바뀝니다.

swyx의 핵심 통찰은 여기서 빛납니다: *"루프를 쌓는다는 것은 안쪽 루프의 출력이 바깥 루프의 입력이 되도록 설계하는 것이다."* 이 딥다이브 시스템이 정확히 그 구조입니다.

### 2. Verification Gap이 여기서도 발생한다 — 그리고 해결책도 내장됐다

AIEWF 2026의 핵심 경고: AI가 쓴 코드 PR의 약 52%는 제대로 검토되지 않는다(Verification Gap). 이 딥다이브 시스템에도 동일한 위험이 있습니다. 에이전트가 쓴 글을 대표님이 매일 아침 읽지 않으면, 품질이 떨어져도 루프는 계속 돕니다. 시스템이 이를 어떻게 해결했는지 보면: **GitHub 커밋 기록**(모든 변경 내역 추적), **텔레그램 알림**(대표님이 폰에서 제목과 인사이트를 스캔), **비서앱 ledger**(green/pink 색상으로 상태 기록). 이 세 겹이 Verification Layer 역할을 합니다. AI가 잘못 실행했을 때 대표님이 개입할 수 있는 최소한의 접점을 유지하는 구조입니다.

swyx의 표현: *"The central problem is not giving up on humans."* 루프를 완전 자율에 넘기는 게 아니라, 인간이 최소 개입으로 최대 관찰을 유지하도록 설계하는 것이 하네스 엔지니어링의 핵심입니다.

### 2-1. L1-L4 루프 스택 구조 — 실전 분류법

Addy Osmani와 AIEWF 2026 워크숍 자료가 공개한 루프 스택 분류법을 이 딥다이브 시스템에 대입해봅니다.

**L1 — Agent Loop (실행 루프)**: 모델이 도구를 호출하며 인지→추론→행동→관찰→추론을 반복하는 가장 안쪽 루프. 이 딥다이브 시스템에서 하루의 글쓰기 자체가 L1입니다. 직접 구축하지 않아도 됩니다 — Claude Code 하네스가 제공합니다.

**L2 — Verification Loop (검증 루프)**: L1 결과를 검증하는 래퍼. 이 시스템에서 GitHub URL 200 확인, 텔레그램 전송 성공 여부 체크가 L2입니다.

**L3 — Event-Driven Loop (이벤트 루프)**: 크론·웹훅·Slack이 에이전트를 트리거합니다. 이 시스템에서 매일 8시 스케줄 자동 실행이 L3입니다. 대표님이 터미널을 열지 않아도 루프가 깨어납니다.

**L4 — Hill-Climbing Loop (자기진화 루프)**: 평가 결과 기반으로 프롬프트·도구·모델 선택이 자동 개선됩니다. 이 시스템에서는 아직 미구현 단계입니다 — 지금 쌓이는 100개+ 딥다이브 데이터가 미래 L4의 훈련 데이터입니다.

Addy Osmani의 표현: *"That inner loop is capability. The outer loop is agency."* 내부 루프는 능력이고, 외부 루프는 자율성입니다. 대표님이 설계해야 할 것은 L3-L4, 즉 외부 루프입니다.

### 3. 루프에는 반드시 "탈출 조건"이 있어야 한다

이 딥다이브 루프의 탈출 조건을 살펴봅니다: 텔레그램 전송 실패 시 2회 재시도 → 그래도 실패하면 ledger에 pink로 기록 후 종료. GitHub URL 200 검증 실패 시 경고를 ledger에 남기고 종료. 이 조건들이 없으면 루프는 "성공처럼 보이지만 실제로는 실패한 상태"를 무한히 반복합니다. swyx가 말한 "Loopcraft의 기예"란 바로 이것입니다 — 언제 계속할지, 언제 멈출지, 언제 에스컬레이션할지를 명확히 코딩하는 능력.

### 4. 루프의 크기는 판단 빈도로 결정된다

왜 이 시스템은 daily 루프인가? 주간이나 시간 단위가 아닌 이유는 하나입니다 — 대표님의 "학습 흡수 주기"가 1일이기 때문입니다. 오전에 읽고, 하루 동안 업무에 적용하고, 다음 날 새 소재를 받을 준비가 됩니다. 루프 주기는 "기술적으로 가능한 가장 짧은 주기"가 아니라 **"아웃터 루프가 처리할 수 있는 속도"** 에 맞춰야 합니다. 시간 단위로 딥다이브가 오면 대표님은 읽지 않습니다. 주 단위로 오면 루틴이 안 됩니다. 일 단위가 최적 주기입니다.

---

## 와당탕/느린호밀 적용 포인트 — 운영 루프 스택 설계도

**오늘 30분 (micro)**: 비서앱에서 지금 가장 자주 반복되는 판단 1개를 골라 다음 3줄을 옵시디언에 씁니다:
- 트리거 조건: "언제 실행되는가?" (예: 매일 오전 9시 / 주문 접수마다)
- 실행 동작: "무엇을 하는가?" (예: 재고 체크 → 주문 확인 메시지 발송)
- 검증 기준: "성공을 어떻게 아는가?" (예: 발송 완료 + 고객 응답)

이 3줄이 Inner Loop 명세서입니다. frontmatter `micro_action`과 동일.

**이번 주 1-2시간 (mid)**: 와당탕/느린호밀 운영 루프 3개를 식별하고 스택으로 구성합니다. 아래 템플릿을 Claude Code 비서앱의 `/ops-stack` 명령으로 구현합니다:

```python
# ops_stack.py — 와당탕 루프 스택 예시
LOOPS = {
    "inner": {
        "trigger": "공구 주문 접수",
        "action": "재고 확인 → 수량 검토 → 배송일 계산",
        "verify": "재고 부족 시 대표님 알림 / 정상이면 자동 처리",
        "interval": "주문마다 (event-driven)"
    },
    "outer": {
        "trigger": "매주 월요일 오전 8시",
        "action": "지난 주 주문 패턴 분석 → 재고 보충 제안",
        "verify": "제안 리포트 ledger 기록 + 슬랙 요약",
        "interval": "주 1회 (cron)"
    },
    "meta": {
        "trigger": "분기마다 대표님 리뷰",
        "action": "inner/outer 루프 기준값 업데이트",
        "verify": "CLAUDE.md 업데이트 + 팀 공유",
        "interval": "분기 1회 (manual)"
    }
}

def run_stack():
    for layer, spec in LOOPS.items():
        result = execute(spec["action"])
        if not verify(result, spec["verify"]):
            escalate_to_owner(layer, result)
```

**이번 달 실험 (macro)**: 느린호밀 콘텐츠 생산 파이프라인을 루프 스택으로 전환합니다. Inner Loop: AI가 소재 수집 + 초안 작성 → Outer Loop: 대표님이 주 1회 모아서 톤 교정 + 선별 → Meta Loop: 월 1회 "어떤 소재가 팔로워 반응이 좋았나" 분석 후 Inner Loop 프롬프트 업데이트. 측정: 대표님 직접 소요 시간 vs. 게시물 반응률.

---

## 한국 솔로 운영자 맥락에서 주의

**루프를 늘릴수록 관리 부채가 쌓입니다.** 와당탕처럼 혼자 운영하는 구조에서 루프를 5개, 10개 만들면 "어떤 루프가 지금 돌고 있는지"를 기억하는 것 자체가 일이 됩니다. swyx의 경고: Verification Gap은 루프 수에 비례합니다. 먼저 1개를 완성하고, 거기서 배운 것으로 다음을 만드세요.

**루프는 "데이터 입력"이 있어야 작동합니다.** 와당탕 ERP가 주문 데이터를 정확히 기록하지 않으면, 그 위에 쌓은 Inner Loop는 잘못된 입력으로 작동합니다. 루프 설계 전에 데이터 수집 습관이 먼저입니다.

---

## 더 깊이 보려면

- [Latent Space: Loopcraft — The Art of Stacking Loops](https://www.latent.space/p/loopcraft)
- [Latent Space: "5 Trends That Defined AI Engineering at World's Fair 2026"](https://www.latent.space/p/aiewf26trends)
- [원본 딥다이브 07-29: swyx Loopcraft 원론](./2026-07-29_deepdive_팟캐스트뉴스레터_swyx-Latent-Space-루프를설계하는자가에이전트시대를지배한다.md)
- [관련 딥다이브 07-24: Cole Medin 자기진화 메모리 — 루프 기억 레이어](./2026-07-24_deepdive_에이전트빌딩_Cole-Medin-자기진화메모리-두번째뇌.md)
- [관련 딥다이브 07-31: IndyDevDan Living Software — 루프가 코드를 배포한다](./2026-07-31_deepdive_에이전트빌딩_IndyDevDan-Living-Software-코드베이스가-스스로-배포된다.md)
- [Geoffrey Huntley: Everything Is a Ralph Loop](https://ghuntley.com/loop/)
- [Addy Osmani: Own the Outer Loop](https://addyosmani.com/blog/own-the-outer-loop/)
- [Boris Cherny & Cat Wu: Claude Code Agent Loops 해설 (The Neuron)](https://www.theneuron.ai/explainer-articles/claude-code-creators-boris-cherny-and-cat-wu-explain-how-to-use-agent-loops/)

---

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "에이전트한테 맡겼더니 잘 됐는지 확인하는 게 더 걱정이다." 루프가 없어서 생기는 문제가 아니라, 루프에 Verification Layer가 없어서 생기는 문제입니다.
- **숫자**: 이 딥다이브 시스템 하나로 100개+ 글, 1000+ 인사이트가 4개월에 쌓였습니다. 루프 1개의 복리 효과입니다.
- **삽질**: 루프 설계 없이 "매일 글 쓰기"를 의지로 시작하면 3주 안에 멈춥니다. 루프는 의지를 시스템으로 바꾸는 장치입니다.
- **훅**: "매일 아침 대표님 폰에 딥다이브가 오는 이유는 의지력이 아닙니다. 루프 때문입니다. Claude Code 총괄 Boris Cherny의 말: '저는 더 이상 Claude에게 프롬프트를 보내지 않습니다. 루프가 보냅니다. 제 일은 루프를 짜는 것입니다.' 오늘 그 루프를 직접 해부합니다."
