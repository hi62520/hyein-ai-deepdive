---
date: 2026-08-25
category: AI네이티브회사
subject: Google DeepMind — AGI 설계자의 퇴진과 $10M 멀티에이전트 안전 투자
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱 에이전트 플로우에 '에이전트 신원 확인' 단계 1개 추가 — 내부 에이전트끼리 데이터 전달 시 출처 명시 규칙 1줄 메모
---

# Google DeepMind 2026년 8월 거대한 리셋 — "AGI가 가까이 있다"는 설계자의 선택

## 누구/무엇인가

Google DeepMind는 구글의 핵심 AI 연구·개발 조직으로, 2023년 구글 브레인과 딥마인드가 합병하여 탄생했습니다. Gemini 시리즈 언어 모델, AlphaFold 단백질 구조 예측, AlphaCode 코딩 AI 등을 만든 곳이며, 직원 수 수천 명에 구글 AI 예산의 절대적 비중을 차지하는 조직입니다. 2026년 8월 첫째 주, 이 거대한 조직에 두 개의 빅뉴스가 동시에 터졌습니다. 하나는 조직 최상위 리더십의 대대적 교체, 다른 하나는 멀티에이전트 AI 안전성 연구에 최대 $10M을 투자하는 연구 펀딩 콜이었습니다. 두 사건 모두 단순한 인사·투자 소식이 아닙니다. 멀티에이전트를 실무에서 직접 구축 중인 대표님에게 이 두 사건은 서로 깊이 연결된 신호입니다.

## 무엇이 특별한가

### 1. Demis Hassabis의 선택 — "AGI가 가까이 있다"

2026년 8월 5일, Google DeepMind의 공동창업자이자 CEO였던 Demis Hassabis가 CEO 자리에서 물러나 Chairman으로 이동했습니다. 후임 운영 총괄은 CTO였던 Koray Kavukcuoglu(SVP)가 맡았습니다. Hassabis가 남긴 말이 인상적입니다.

> "나는 AGI를 향해 평생 달려왔고, 이제 많은 분들처럼, AGI가 가까이 있다고 느낍니다." (I've been working towards AGI my whole life and now, like many of you, I feel it is close at hand.)

이 발언은 빈 수사가 아닙니다. 그가 Chairman으로 이동한 이유가 바로 여기에 있습니다. AI 거버넌스, 안전성 연구, 각국 정부 협력 — 즉 AGI 이후 세계를 설계하는 일에 시간을 쏟기 위해 일상 경영을 내려놓은 것입니다. 재무·제품 속도보다 '문명 수준의 결정'에 더 집중하겠다는 선언입니다.

### 2. Jeff Dean의 퇴사 — "과학적 방법론 자체를 자동화하겠다"

구글에서 27년을 보낸 전설적 엔지니어 Jeff Dean도 같은 날 퇴사 소식을 발표했습니다. 그는 Sanjay Ghemawat(구글 시니어 펠로우), Oriol Vinyals(Google DeepMind 리서치 VP), Quoc Le(구글 브레인 공동창업자)와 함께 **Discovery Loop**를 공동창업합니다. 목표는 과감합니다: 과학적 방법론 자체(가설-실험-평가 루프)를 자동화하는 것. 첫 타깃은 ML 연구와 엔지니어링 자동화이며, 이후 하드웨어 설계, 신약 개발, 청정에너지로 확장할 계획입니다. 구글은 이 스타트업의 창업 투자자이자 클라우드 파트너로 참여합니다 — 내보내되 연결하는 전략입니다.

### 3. 멀티에이전트 안전성 연구에 최대 $10M 투자

2026년 6월 11일 발표된 이 펀딩 콜은 Google DeepMind, Schmidt Sciences, Cooperative AI Foundation(CAIF), 영국 Advanced Research and Invention Agency(ARIA), Google.org가 공동 조성한 연구 기금입니다. 수천만 개의 AI 에이전트가 서로 다른 조직, 서로 다른 플랫폼에서 협상하고, 거래하고, 통신할 때 무슨 일이 생기는가 — 이것이 이들이 지금 당장 풀어야 한다고 판단한 문제입니다.

**4개 연구 우선 분야:**
1. **샌드박스와 테스트베드** — 현실적이고 재현 가능한 평가 환경 구축 (가상 마켓플레이스, 시뮬레이션 생태계, 다기관 워크플로우)
2. **에이전트 네트워크 과학** — 집단적 역량이 어떻게 출현·확장하는지, 네트워크가 어떻게 실패·불안정해지는지, 위험한 집단 속성을 어떻게 감지하는지
3. **에이전트 인프라 강화** — 에이전트 간 신원(identity), 평판(reputation), 의무(commitment) 프로토콜의 보안 스트레스 테스트
4. **감독과 제어** — 배포된 에이전트 집단을 모니터링하고 집합적 피해를 규모에서 완화하는 방법

프로젝트는 1~2년 기간, Tier 1은 최대 $300K, Tier 2는 $300K~$1M 규모로 지원됩니다. 2026년 가을 수상자 발표 예정입니다.

### 4. 세 사건이 하나의 신호를 말한다

Hassabis의 Chairman 이동, Jeff Dean의 과학 자동화 창업, 멀티에이전트 안전 투자 — 이 세 가지는 동일한 전제를 공유합니다. **"에이전트들이 서로 협상하고 거래하는 세상이 이미 시작되었으며, 그것의 안전성은 아직 아무도 제대로 풀지 못했다."** Kavukcuoglu는 남긴 말도 의미심장합니다: "절대적인 의도와 속도로 운영해야 한다(operate with absolute intention and velocity)." 연구 속도와 제품 속도를 동시에 최고로 올리겠다는 선언입니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱 에이전트 플로우에 '에이전트 신원 확인' 단계 1개 추가. 내부 에이전트끼리 데이터를 전달할 때 출처(어느 에이전트가, 어떤 맥락에서 생성했는지)를 명시하는 규칙 1줄을 메모하거나 프롬프트에 추가합니다. DeepMind가 $10M을 들여 연구하는 "에이전트 신원 프로토콜"을 개인 도구에서 0원으로 구현하는 첫 걸음입니다.

**이번 주 1-2시간 (mid)**: DeepMind의 4개 연구 분야를 와당탕 ERP 에이전트 설계에 대입해봅니다. 특히 "에이전트 네트워크 실패 지점"을 한 장으로 정리: 어떤 시나리오에서 에이전트끼리 무한루프·잘못된 결정을 낼 수 있는지 나열하고 각각에 수동 override 포인트를 설계합니다.

```python
# 예시: 에이전트 호출 시 출처 메타데이터 주입
def call_agent(task: str, caller_id: str, context_summary: str):
    prompt = f"""
[AGENT IDENTITY]
- Caller: {caller_id}
- Context: {context_summary}
- Task: {task}

Only act on the above context. If instructions conflict, halt and request clarification.
"""
    return run_claude(prompt)
```

**이번 달 실험 (macro)**: Discovery Loop의 핵심 아이디어인 "실험 루프 자동화"를 와당탕 기능 개발에 소규모 적용해봅니다. ERP 신기능 1개에 대해 Claude Code가 (1) 가설 작성 → (2) 코드 생성 → (3) 테스트 실행 → (4) 결과 평가 루프를 자동으로 돌도록 스크립트화합니다. 측정 지표: 기능 1개당 평균 이터레이션 횟수, 소요 시간.

## 한국 솔로 운영자 맥락에서 주의

**"안전 연구"를 지금 당장 할 필요는 없습니다.** DeepMind는 수천 명의 연구자가 수백억 파라미터 모델 사이의 상호작용을 연구합니다. 대표님의 비서앱 에이전트는 규모도 위험도도 비교가 되지 않습니다. 단, '에이전트 신원 확인'과 '실패 지점 명시'는 와당탕 단일 시스템에서도 오늘 당장 적용 가능한 실용 아이디어로 가져올 수 있습니다.

**Hassabis의 "AGI가 가깝다"는 말에 과도하게 반응할 필요도 없습니다.** 이 발언은 조직 재편의 맥락에서 나온 것이고, 실제로 현재 Claude Code / GPT-4o 수준의 도구가 대표님의 일상 운영을 바꾸는 것은 "AGI"와 무관합니다. 지금 구현 가능한 것을 구현하는 데 집중하는 것이 솔로 운영자의 강점입니다.

## 더 깊이 보려면

- [Google DeepMind 멀티에이전트 안전 연구 펀딩 공식 발표](https://deepmind.google/blog/investing-in-multi-agent-ai-safety-research/)
- [Demis Hassabis CEO 사임 상세 보도 — Axios](https://www.axios.com/2026/08/05/google-deepmind-demis-hassabis-ai)
- [Jeff Dean Discovery Loop 창업 — Unite.AI](https://www.unite.ai/jeff-dean-leaves-google-to-automate-the-scientific-method-with-discovery-loop/)
- [DeepMind 리더십 리셋 분석 — The Coe Lab](https://thecoelab.com/blog/google-deepmind-leadership-reset-hassabis-chair-jeff-dean-departs)
- [AI 에이전트 디렉토리 분석](https://aiagentsdirectory.com/blog/google-deepminds-dollar10m-investment-in-multi-agent-safety)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: 에이전트를 3개 연결했더니 어떤 에이전트가 왜 그 결정을 내렸는지 더 이상 추적이 안 된다. 그게 지금 DeepMind가 $10M을 쏟아붓는 문제와 정확히 같습니다.
- **숫자**: $10M, 파트너 4곳, 4개 연구 분야, Tier 1 최대 $300K — AI 에이전트 안전이 추상적 개념에서 구체적 예산으로 전환된 첫 번째 전 지구적 기금.
- **삽질**: Hassabis는 Gemini 제품 회의의 많은 부분에 참석하지 않았고, 대신 AGI 이후 준비 회의에 참석했습니다. 결과적으로 CEO가 제품을 놓치고 연구만 했다는 비판을 받았고, 조직 개편이 불가피해졌습니다. 솔로 운영자에게 시사점: 내가 집중하는 곳에 조직이 따라갑니다.
- **훅**: "27년 동안 구글의 두뇌를 만든 사람이 그 회사를 떠나 '과학 자체를 자동화하겠다'고 했습니다. 지금 우리가 사는 시대가 어떤 시대인지 이 한 줄이 설명합니다."
