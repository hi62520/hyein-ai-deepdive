---
date: 2026-11-03
category: AI네이티브회사
subject: Replit — Self-Driving Company, 에이전트가 회사를 운영한다
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱에서 "에이전트 작업 로그" 메모 노드 1개 만들고, 오늘 Claude Code 에이전트가 처리한 작업 3개를 직접 기록해보기
---

# Replit — Self-Driving Company, 에이전트가 회사를 운영한다

## 누구/무엇인가

Replit은 2016년 Amjad Masad(요르단 출신 이민자 창업자)가 설립한 클라우드 기반 코딩·배포 플랫폼입니다. 처음에는 브라우저에서 바로 코드를 실행할 수 있는 개발 환경으로 시작했지만, 2024~2026년 사이에 완전히 다른 회사로 탈바꿈했습니다. 2026년 3월 Agent 4 출시와 함께 $400M 시리즈D를 유치하며 기업가치 $9B를 달성했고, 현재 $1B ARR(연간반복매출)을 목표로 질주 중입니다. Masad는 2026년 10월 TechCrunch Disrupt에서 "2030년까지 AI 에이전트가 회사를 직접 운영하게 될 것"이라는 비전을 발표했습니다. Anthropic과의 독점 파트너십을 끊고 멀티모델 전략을 선언한 것도 이 무렵입니다. 사용자 수 3,000만 명, 재학생부터 솔로 창업자까지 폭넓은 기반 위에서 에이전트 기반 소프트웨어 민주화를 실험하고 있습니다.

## 무엇이 특별한가

**1. Agent 4: 병렬 에이전트 + 무한 캔버스**

2026년 3월에 출시한 Agent 4는 단순한 코드 생성기가 아닙니다. 여러 서브 에이전트가 동시에 다른 작업을 처리하고, 충돌이 생기면 전담 에이전트가 자동으로 해결합니다. Masad는 직접 X에 이렇게 썼습니다: *"Software isn't merely technical work anymore. It's creative. Agent 4 — the first AI built for creative collaboration between humans and agents. Design on an infinite canvas, work with your team, run parallel agents, and ship working apps, sites, slides & more."* 기존 프롬프트 → 선형 응답 구조를 깨고, 2D 캔버스에서 UI를 스케치하고 컴포넌트를 연결하며 팀원과 동시에 작업하는 방식입니다. 런칭 직후 "Agent 3 대비 10배 빠르다"고 주장했습니다.

**2. Self-Driving Company: 에이전트가 야근한다**

Masad의 핵심 테제는 "에이전트가 소프트웨어를 만드는 것을 넘어 회사 운영 전체를 담당해야 한다"입니다. 실제로 Replit 내부에서는 매일 밤 에이전트가 전체 사용자 트레이스를 읽고, 버그를 찾아 PR을 생성하고, A/B 테스트로 배포한 뒤 루프를 닫습니다. 인간 엔지니어는 "배포 직전에만 코드를 확인한다"고 Masad는 밝혔습니다. 이 내부 자동화 덕분에 2026년 상반기 동안 엔지니어당 코드 생산성이 약 3배 향상됐다고 주장했습니다(자체 집계, 외부 검증 未완료).

**3. Agent Habitat: 에이전트를 위한 인프라 레이어**

2026년 10월 TechCrunch Disrupt에서 공개한 "Replit for Business"와 "Agent Habitat" 개념은 에이전트가 회사 내부에서 안전하게 일하기 위한 인프라입니다. 4가지 레이어로 구성됩니다: ① 오케스트레이션(어떤 에이전트가 무엇을 맡을지), ② 샌드박싱(격리 실행 환경), ③ 에러 복구(App Monitoring, 2026년 4월 출시), ④ 아이덴티티 추적(모든 에이전트 실행에 고유 토큰 부여, 모든 액션 감사 로그). 특히 아이덴티티 추적은 기업 보안 감사에서 "누가 이 코드를 배포했는가?"라는 질문에 AI가 답할 수 있게 해줍니다. Masad는 이를 "자율주행차에 블랙박스를 다는 것"에 비유했습니다.

**4. 멀티모델 전환: Anthropic 결별 선언**

Replit은 과거 Anthropic 모델을 기본으로 사용했으나, 2026년 하반기 TechCrunch Disrupt에서 Masad는 "더 이상 Anthropic과 일하지 않는다"고 선언했습니다. 특정 모델 제공사에 종속되지 않고, 각 작업에 가장 적합한 모델을 선택하는 멀티모델 오케스트레이션 전략을 채택한 것입니다. 이는 에이전트 플랫폼 레이어가 모델 레이어보다 높은 가치를 갖는다는 Masad의 판단을 반영합니다.

**5. $9B 기업가치의 역설: 수익 모델의 변형**

Agent 4는 구독($20/월 Core, $100/월 Pro) 외에 에포트 크레딧 방식을 추가했습니다. 에이전트가 수행하는 작업 복잡도에 따라 크레딧이 소비되며, 이는 사용자 입장에서 비용 예측을 어렵게 만들지만 Replit 입장에서는 실제 가치 창출(에이전트 실행)에 직결된 수익 모델을 확보한 것입니다. 솔로 창업자가 밤새 에이전트를 돌려 스타트업 MVP를 만드는 사용 패턴이 이 모델에서 ARR 폭발을 가능하게 했습니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱에서 "에이전트 작업 로그" 메모 노드 1개 만들고, 오늘 Claude Code 에이전트가 처리한 작업 3개를 직접 기록해보기. Agent Habitat의 아이덴티티 추적 개념을 최소 버전으로 실행하는 것입니다.

**이번 주 1-2시간 (mid)**: 와당탕 ERP의 특정 반복 작업(예: 메모 분류, 일일 정산 체크)을 Replit 스타일 서브 에이전트 분리 방식으로 재설계. 현재 단일 프롬프트 → 단일 응답 패턴을 "서브태스크 1(수집) → 서브태스크 2(분류) → 서브태스크 3(요약)" 3단계 병렬 가능 구조로 분리하는 플로우 설계서 1장 작성.

```python
# 와당탕 에이전트 분리 예시 (의사코드)
tasks = [
    {"id": "collect", "agent": "memo_reader", "input": today_memos},
    {"id": "classify", "agent": "category_tagger", "depends_on": "collect"},
    {"id": "summarize", "agent": "daily_digest", "depends_on": "classify"},
]
# 각 태스크에 고유 토큰 부여 → 감사 로그 기록 (Replit Agent Habitat 방식)
for t in tasks:
    t["run_id"] = generate_token(t["id"], timestamp=now())
```

**이번 달 실험 (macro)**: 느린호밀 콘텐츠 파이프라인에 "야간 에이전트 루프" 파일럿 도입. Replit 내부처럼 매일 밤 에이전트가 최근 7일 비서앱 로그를 읽고, 미완성 메모를 정리해 draft 1개를 생성하는 루틴 설계 및 2주 실험. 측정 지표: ① 주간 초안 생성 수, ② 대표님이 직접 편집한 시간 (목표: 3시간 → 1시간 이하).

## 한국 솔로 운영자 맥락에서 주의

**기업용 스케일 함정**: Agent Habitat와 Self-Driving Company 비전은 수십 명의 엔지니어가 있는 조직을 전제로 합니다. 대표님처럼 혼자 운영하는 경우, 4레이어 거버넌스 구조를 통째로 이식하면 관리 비용이 가치를 초과합니다. 핵심 개념인 "에이전트마다 고유 ID + 감사 로그"만 선택적으로 차용하는 것이 현실적입니다.

**크레딧 비용 불예측성**: 에포트 크레딧 방식은 병렬 에이전트를 많이 돌릴수록 비용이 급증합니다. 대표님이 와당탕 ERP 자동화를 Replit 위에서 구축할 경우, 월 $20 Core 플랜만으로는 실제 운영이 불가능하고 $100 이상이 될 수 있습니다. Claude Code 로컬 실행과 병행 비교가 필수입니다.

## 더 깊이 보려면

- [Replit CEO: The Self-Driving Company (The New Stack)](https://thenewstack.io/replit-self-driving-company/)
- [Agent 4 Launch + $400M Raise (TBPN)](https://www.tbpndigest.com/story/2026-03-11/amjad-masad-on-replit-agent-4-launch-and-400m-raise)
- [Forbes: $9B AI Company Reimagining Vibe Coding](https://www.forbes.com/sites/richardnieva/2026/03/11/meet-the-9-billion-ai-company-reimagining-vibe-coding-replit-amjad-masad/)
- [Amjad Masad X: Agent 4 공식 발표](https://x.com/amasad/status/2031755113694679094)
- [Per-Agent Identity Tracking (TechTimes)](https://www.techtimes.com/articles/329514/20261027/replit-deploys-per-agent-identity-tracking-close-enterprise-ai-governance-gap.htm)
- [Platformer: Replit CEO Interview — Coding, Design, Jobs](https://www.platformer.news/replit-amjad-massad-interview-coding-design-jobs/)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "에이전트가 코드를 쓰는 건 됐는데, 그게 어제 밤 뭘 했는지 아무도 모른다." — 팀이 없는 솔로 운영자는 에이전트가 저지른 실수를 되짚을 방법이 없습니다. Replit이 Agent Habitat에서 가장 먼저 푼 문제가 바로 이것입니다.
- **숫자**: 엔지니어당 코드 생산성 3배 향상 + 제품 인시던트 동결(2026 상반기, Replit 자체 집계). 하지만 외부 검증 없음 — "자체 집계"를 강의에서 다루면 신뢰성 비판 포인트로도 쓸 수 있습니다.
- **삽질**: Anthropic과 파트너십을 맺고 단일 모델에 의존했다가 멀티모델로 방향을 틀었습니다. 플랫폼 사업자가 모델 사업자와 공생하면서도 종속되지 않는 경계선이 어디인지를 보여주는 실제 사례입니다.
- **훅**: "매일 밤 에이전트가 당신 회사의 버그를 찾고, PR을 올리고, 배포까지 합니다. 당신이 자는 동안. Replit은 이미 그렇게 하고 있습니다. 와당탕은 언제 시작할 건가요?"
