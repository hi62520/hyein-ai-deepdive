---
date: 2026-09-29
category: AI네이티브회사
subject: Linear (Karri Saarinen) — 이슈 트래커의 죽음과 에이전트 관제탑의 탄생
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱 ERP에서 가장 반복적인 버그 유형 1가지를 적어두고, "이 버그를 Linear Agent라면 어떤 컨텍스트를 갖고 있어야 자율 해결할까?" 30분 안에 메모 1장 작성
---

# Linear (Karri Saarinen) — 이슈 트래커의 죽음과 에이전트 관제탑의 탄생

## 누구/무엇인가

Linear는 2019년 Karri Saarinen(CEO), Jori Lallo(CTO), Tuomas Artman(CTO 공동창업자)이 만든 제품 개발 소프트웨어입니다. 창업 당시 목표는 단 하나였습니다: Jira보다 빠른 이슈 트래커. 실제로 Linear는 극도의 속도와 미니멀한 디자인으로 Notion, Jira에 지친 엔지니어 팀들의 마음을 사로잡았고, OpenAI, Loom, Vercel, Scale AI 등 수백 개의 테크 스타트업을 고객으로 확보했습니다.

2026년 3월 24일, Saarinen은 에세이 하나를 발행합니다. 제목은 **"Issue Tracking is Dead(이슈 트래킹은 죽었다)"**. 자신이 만든 제품의 범주를 스스로 사망 선고한 것입니다. 그리고 그 자리에 새 개념을 내놓았습니다: **Agent Management(에이전트 관리)**. 에이전트들이 이제 소프트웨어 개발의 대부분을 처리하는 시대에, 프로젝트 관리 도구는 더 이상 인간의 할 일 목록이 아니라 **에이전트에게 끊임없이 컨텍스트를 공급하는 오케스트레이션 허브**가 되어야 한다는 주장입니다.

## 무엇이 특별한가

### 1. "이슈 트래커는 죽었다" — 범주 자살로 새 시장을 연다

Saarinen의 선언은 단순한 마케팅이 아닙니다. 그의 핵심 논리는 이렇습니다: AI 코딩 에이전트가 소프트웨어 개발의 대부분을 수행하게 되면, 기존 이슈 트래커는 인간이 할 일을 나눠 갖는 도구에 불과합니다. 에이전트는 티켓을 읽는 것이 아니라 **컨텍스트를 소비**합니다. "이 버그는 무엇인가"가 아니라 "이 버그는 어떤 코드베이스에서, 어떤 사용자 행동으로, 어떤 서비스와 연결되어 발생했는가"를 알아야 합니다. Linear가 쌓아온 이슈·코드·팀 히스토리가 바로 그 컨텍스트 창고입니다. 범주를 죽임으로써 더 큰 시장을 선점한 것입니다.

*"Agents make software development a lot simpler as they do more of the procedural work. What we're building now is an orchestration hub — the place where agents work alongside humans."* — Karri Saarinen, March 2026

### 2. Linear Agent: 버그 리포트의 30%를 인간이 보기 전에 처리한다

2026년 3월 Linear Agent가 출시되고, 6월에 **Coding Sessions**가 추가됩니다. Coding Sessions는 "이슈에서 diff까지"를 에이전트가 독자적으로 처리하는 기능입니다. 에이전트는 보안된 클라우드 환경에서 코드를 작성하고, Sentry·Datadog에서 증거를 수집하고, 코드베이스를 추적해 근본 원인을 파악한 뒤 PR을 열어 리뷰를 요청합니다.

**Linear가 자사에서 직접 이 워크플로우를 사용한 결과**: 신규 버그 리포트의 약 **30%**를 에이전트가 첫 번째 패스에서 해결합니다. 인간 엔지니어에게 도달하기 전에 이미 처리가 완료됩니다. Loom이 영상 편집을 줄이는 것처럼, Linear는 이슈 해결 자체를 자동화하기 시작한 것입니다.

### 3. Diffs: 코드 리뷰가 Linear 안으로 들어온다

6월에 함께 출시된 **Diffs**는 에이전트가 생성한 PR을 GitHub·GitLab을 떠나지 않고 Linear 안에서 리뷰할 수 있게 합니다. "이슈가 어떤 코드로 해결됐는가"의 맥락이 같은 화면에 붙어 있습니다. 에이전트가 만든 코드는 그 이슈의 히스토리, 연결된 팀 논의, 이전 관련 버그 기록과 함께 리뷰됩니다. 단순한 diff 뷰어가 아니라 **컨텍스트 위에 올라간 코드 리뷰**입니다.

### 4. CI 재설계: 에이전트가 병목을 새로 만들었다

2026년 9월 21일, CTO Tuomas Artman이 Linear의 CI 시스템 전면 재설계를 발표합니다. 이유가 인상적입니다: AI 에이전트가 PR을 대량으로 생성하면서 **테스트 스위트가 2026년 동안 거의 4배로 늘었고**, 기존 CI는 이를 감당하지 못했습니다. 재설계 결과 테스트 러너 시간은 약 50% 단축됐고, PR 대기 시간은 6분 이상에서 약 5분으로 줄었습니다. 에이전트가 개발 속도를 높이자, 검증 인프라가 새 병목이 된 것입니다. **에이전트 도입 → 새 병목 발견 → 인프라 재설계** 사이클을 Linear는 이미 자사에서 경험하고 있습니다.

### 5. 모델 라우팅: 토큰을 아껴야 에이전트를 더 쓴다

9월 24일 출시된 "New controls for Linear coding agent"는 작업 복잡도에 따라 에이전트가 사용하는 모델을 자동 선택하게 합니다. 단순한 작업에는 빠른 모델, 복잡한 추론에는 강한 모델. 또한 오픈 웨이트 모델(GLM 기반)도 지원하기 시작했습니다. Coding Sessions 과금 구조는 모델 토큰 비용은 원가 그대로(마크업 없음), 샌드박스 런타임은 20분 블록당 $0.25로 분리됐습니다. **AI 크레딧 소모를 투명하게 만들어 팀이 에이전트를 더 많이 돌릴 수 있는 심리적 조건을 만드는 것**입니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱 ERP에서 가장 반복적으로 발생하는 버그 유형 1가지를 선정하고, "이 버그를 Linear Agent라면 어떤 컨텍스트를 갖고 있어야 자율 해결할까?"를 메모 1장으로 작성합니다. 에러 발생 맥락(어떤 액션, 어떤 데이터 상태, 연결된 API), 관련 코드 파일명, 기대 해결 방식을 3줄로 정리하면 Claude Code 프롬프트의 원형이 됩니다.

**이번 주 1-2시간 (mid)**: Claude Code 세션에서 반복 버그 하나에 대해 "이슈 카드"를 만들어 봅니다. 에러 로그 + 발생 조건 + 관련 파일 경로를 하나의 마크다운 파일(`.claude/issues/` 폴더)에 정리하고, CLAUDE.md에 "버그 이슈 파일이 있으면 먼저 읽을 것"을 추가합니다. Linear의 컨텍스트 창고 개념을 Claude Code 프로젝트 안에 이식하는 실험입니다. 예시 스니펫:

```markdown
# ISSUE-001: 주문 중복 저장 버그
**발생 조건**: 네트워크 지연 시 submit 버튼 2회 클릭
**관련 파일**: src/orders/submit.ts, api/routes/orders.ts
**에러 로그 패턴**: "duplicate key value violates unique constraint"
**기대 해결**: idempotency key 도입 또는 submit 버튼 debounce
```

**이번 달 실험 (macro)**: 비서앱·ERP의 Claude Code 세션에 "이슈 로그" 폴더를 만들고 실제 버그 5-10개를 이슈 카드 형식으로 관리합니다. 한 달 후 Claude Code가 이슈 카드를 참조했을 때와 안 했을 때 해결 속도·정확도를 비교합니다. 측정 지표: (a) 첫 번째 제안이 바로 적용 가능한 비율, (b) 추가 질문 없이 해결된 버그 수, (c) 같은 버그 재발 빈도.

## 한국 솔로 운영자 맥락에서 주의

**첫째, 팀이 없으면 에이전트 관리의 이점이 반감됩니다.** Linear Agent의 핵심 가치는 인간 엔지니어 팀이 에이전트와 협업하는 구조에서 빛납니다. 솔로로 운영할 경우 에이전트가 생성한 PR을 자신이 직접 리뷰해야 하고, 코드 리뷰 자체가 새 병목이 될 수 있습니다. 와당탕·느린호밀처럼 1인 운영 구조에서는 "에이전트가 30% 해결"이 아니라 "에이전트가 제안하고 대표님이 수락/거절하는 구조"로 재설계가 필요합니다. 에이전트 자율도를 점진적으로 높이되, 초반에는 반드시 인간 승인 게이트를 유지하세요.

**둘째, $0.25/20분 과금 구조는 실험 시작엔 저렴하지만 규모화되면 비쌉니다.** 와당탕 수준에서 Coding Sessions를 월 100회 돌리면 샌드박스 비용만 $25 이상입니다. 모델 토큰 비용은 별도입니다. Claude Code로 직접 구현하는 현재 방식이 비용 면에서 더 효율적일 수 있으며, Linear는 팀 규모가 5인 이상이 된 시점에 진지하게 검토하는 것이 적절합니다.

## 더 깊이 보려면

- [Linear Changelog — Introducing Linear Agent (2026-03-24)](https://linear.app/changelog/2026-03-24-introducing-linear-agent)
- [Linear — Coding Sessions 공식 문서](https://linear.app/docs/coding-sessions)
- [Linear Now — AI updates](https://linear.app/now/ai)
- [devclass: Linear moves sideways to agentic AI as CEO declares issue tracking dead](https://www.devclass.com/development/2026/03/27/linear-moves-sideways-to-agentic-ai-as-ceo-declares-issue-tracking-dead/5211661)
- [explainx.ai: Linear CI Rework — Agent Bottleneck Fixes (Sep 2026)](https://explainx.ai/blog/linear-ci-rework-agentic-coding-bottleneck-2026)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: 에이전트가 코드를 쓰기 시작하자 버그 리포트가 쌓이는 속도보다 PR이 생성되는 속도가 빨라졌다. 기존 CI가 병목이 됐다. 해결한다고 만든 도구가 새 문제를 만들었다.
- **숫자**: Linear 내부에서 신규 버그 리포트의 **30%**를 에이전트가 첫 패스에서 해결 — 인간 엔지니어에게 도달하기 전에. 테스트 스위트는 2026년 동안 **거의 4배** 증가.
- **삽질**: Saarinen이 2019년 "Jira보다 빠른 이슈 트래커"를 만들었다가, 2026년 스스로 "이슈 트래킹은 죽었다"고 선언. 자신의 제품 범주를 사망 선고해야 다음 시장이 보였다.
- **훅**: "당신이 쓰는 할 일 목록, 에이전트는 읽지 않습니다. 에이전트는 '왜 이 버그가 생겼는가'의 맥락을 소비합니다. 당신 프로젝트에 그 맥락이 쌓여 있나요?"
