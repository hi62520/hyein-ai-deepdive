---
date: 2026-07-05
category: 주간종합
subject: Brockman 판단 큐 실전 이식 — "주의력이 희소 자원"을 비서앱 설계도로 번역하다
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱(또는 CLAUDE.md)에 "AI 자율 실행 허용 목록"과 "반드시 내가 승인할 목록"을 각 5개씩 지금 적어두기 — 판단 큐의 씨앗이 됩니다
---

# Brockman 판단 큐 실전 이식 — "주의력이 희소 자원"을 비서앱 설계도로 번역하다

## 이번 주에서 왜 이 주제인가

목요일(7월 3일) 딥다이브에서 Greg Brockman의 핵심 명제를 정리했습니다. "실행은 이제 쉬워졌다. 인간에게 남는 병목은 단 하나, 판단이다." 그 글은 "오늘 할 업무 목록을 AI 위임 항목과 내 판단 항목으로 나눠라"는 micro_action으로 마무리했습니다.

그런데 수요일(7월 1일) Nathan Labenz 딥다이브가 이 명제에 데이터로 이의를 제기합니다. 6,000명 조사에서 87%가 AI를 쓰고 있고, 73%가 "생산성이 높아졌다"고 답하면서도, 실질 성과 개선은 **단 13%의 조직**에서만 나왔습니다. 이유는 하나입니다. 주당 **6.4시간을 보트시팅**(맥락 붙여넣기, 오류 디버깅, 잘못된 답변 정리)에 쓰고 있기 때문입니다.

두 발언을 겹치면 역설이 등장합니다. Brockman은 "판단 큐를 만들면 주의력이 해방된다"고 했습니다. Labenz는 "판단 큐를 잘못 만들면 그 큐 자체가 새로운 보트시팅이 된다"고 말하는 셈입니다. **판단 큐는 해방의 도구일 수도 있고, 또 다른 주의력 낭비가 될 수도 있습니다.** 오늘의 각도는 바로 여기입니다. 큐를 어떻게 설계해야 해방이 되는가.

## 판단 큐가 고장나는 방식: 승인 피로

현장에서 확인된 가장 흔한 실패 패턴은 "모든 것을 판단 큐에 올리는" 설계입니다. 에이전트가 캘린더를 읽을 때마다, 이메일을 분류할 때마다, 요약을 생성할 때마다 승인을 요청하면 어떻게 될까요? 2026년 현장 연구들이 공통으로 지적하는 현상이 발생합니다. "승인 피로(Approval Fatigue)" — 검토를 무의미하게 자동 승인하는 반사 반응이 생깁니다.

> **"Checkpoint fatigue is real. Past a certain ratio, the oversight model breaks entirely."**
>
> (체크포인트 피로는 실재합니다. 승인 비율이 임계치를 넘으면 감시 모델 자체가 완전히 붕괴합니다.)

이것이 Nathan Labenz의 69% 수치와 연결됩니다. 설문 응답자의 69%가 "완전히 이해하거나 방어할 수 없는 AI 생성 결과물을 제출한 경험이 있다"고 인정했습니다. AI 결과물을 검토도 안 하고 통과시키는 사람들 — 이것은 그들이 나쁜 것이 아닙니다. 판단 큐를 잘못 설계한 탓입니다.

## 판단 큐 설계의 두 축: 가역성 × 영향도

2026년 AWS AI Well-Architected 프레임워크와 Anthropic의 에이전트 설계 원칙이 공통으로 제시하는 기준이 있습니다. **"가역성(Reversibility)"과 "영향도(Impact)"** 두 축으로 에이전트 행동을 분류하라는 것입니다.

Anthropic은 이것을 "**최소 발자국(Minimal Footprint)**" 원칙으로 명문화했습니다. 에이전트는 필요한 최소한의 권한만 요청하고, 가역적 행동을 비가역적 행동보다 우선하며, 범위가 불확실할 때 사람에게 확인해야 합니다.

이 두 축을 와당탕·느린호밀 맥락으로 번역하면 다음 4분면이 나옵니다:

| | **가역적** | **비가역적** |
|---|---|---|
| **저영향** | ✅ 자율 실행 (감사 로그만) | 📋 사후 알림 |
| **고영향** | 🔔 비동기 알림 | 🛑 동기 승인 (차단) |

- **자율 실행 (Autonomous)**: 오류 수정, 일정 초안, 요약 생성. 틀려도 금방 고칩니다. 여기에 승인을 넣으면 보트시팅만 만들어집니다.
- **비동기 알림 (Async Notify)**: 고객 응답 초안, 재고 알림. 에이전트가 초안을 만들어두고 대표님이 여유될 때 확인합니다. 아침에 일어나 커피 한 잔 하면서 훑어보면 됩니다.
- **동기 승인 (Sync Gate)**: 외부 발행(SNS 포스팅), 결제 실행, 계약 발송. 이것만 진짜 판단 큐에 올립니다.
- **사후 알림 (Post-Audit)**: 자율 실행했지만 가역적이지 않은 경우 — 예: 자동 발주. 즉시 알림만 보내고 대표님이 원하면 취소 버튼을 누를 수 있게 합니다.

## 3가지 판단 큐 아키텍처

에이전트 설계에서 쓸 수 있는 판단 큐 패턴은 3가지입니다.

**1. 동기 게이트(Synchronous Gate)**: 에이전트가 멈추고 승인을 기다립니다. 최대 통제력, 하지만 지연이 생깁니다. 비가역·고영향 행동에만 씁니다. 와당탕 예: 외부 결제 API 호출 직전 차단.

**2. 비동기 에스컬레이션(Async Escalation)**: 에이전트는 다른 태스크를 계속 진행하면서 승인 대기 항목을 알림으로 올립니다. 아침 비서앱 대시보드에 "승인 대기 3건"이 표시됩니다. 와당탕 예: 고객 견적 초안 3개 → 아침에 1개 선택.

**3. 병렬 피드백(Parallel Feedback)**: 에이전트가 실행하면서 동시에 사람이 검토합니다. 사람이 거부하면 롤백합니다. 가장 낮은 지연, 하지만 롤백 로직 구현이 필요합니다. 와당탕 예: SNS 예약 발행 → 30분 내 취소 가능 창.

이 세 패턴을 쓰면, 진짜 판단이 필요한 항목만 대표님의 화면에 나타납니다. **큐의 신호 대 잡음비가 높아질수록 큐에 대한 신뢰가 올라갑니다.**

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱이나 CLAUDE.md에 두 목록을 작성합니다. "AI 자율 실행 허용 목록" 5가지(예: 요약 생성, 일정 초안, 재고 현황 알림 문자 초안, SNS 초안, 영수증 정리)와 "반드시 내가 승인할 목록" 5가지(예: 외부 결제, 고객에게 발송되는 모든 공식 문서, SNS 실제 게시, 계약서 서명, 직원에게 보내는 메시지). 이 두 목록이 판단 큐의 씨앗입니다. `micro_action`과 동일합니다.

**이번 주 1-2시간 (mid)**: Claude Code로 비서앱에 "판단 큐 레이어"를 구현합니다. 에이전트 태스크 완료 시 `requires_human_approval` 필드를 기준으로 자동 분류합니다. 아래 스니펫이 시작점입니다.

```python
from enum import Enum

class AgentActionTier(Enum):
    AUTONOMOUS = "autonomous"      # 자율 실행, 로그만
    ASYNC_NOTIFY = "async_notify"  # 비동기 알림
    SYNC_GATE = "sync_gate"        # 동기 승인 필요
    POST_AUDIT = "post_audit"      # 실행 후 사후 알림

def classify_action(action: dict) -> AgentActionTier:
    reversible = action.get("reversible", True)
    high_impact = action.get("high_impact", False)
    external = action.get("external_publish", False)

    if external or (not reversible and high_impact):
        return AgentActionTier.SYNC_GATE
    if high_impact and reversible:
        return AgentActionTier.ASYNC_NOTIFY
    if not reversible and not high_impact:
        return AgentActionTier.POST_AUDIT
    return AgentActionTier.AUTONOMOUS

# 비서앱 대시보드에 sync_gate 항목만 뱃지로 표시
def get_pending_approvals(tasks: list[dict]) -> list[dict]:
    return [
        t for t in tasks
        if classify_action(t) == AgentActionTier.SYNC_GATE
        and not t.get("approved", False)
    ]
```

**이번 달 실험 (macro)**: 판단 큐 설계 후 두 가지 지표를 매주 기록합니다. 첫째, "하루에 대표님이 실제로 결정한 건수(판단 밀도)". 둘째, "결정당 소요 시간". 목표는 Brockman의 비전대로 가는 것 — 판단 건수는 줄이되 각 판단의 영향력은 커지는 방향. Gartner 예측에 따르면 2026년 말까지 기업 앱의 40%에 태스크 특화 에이전트가 포함됩니다. 이 설계를 지금 비서앱에 심어두면 6개월 뒤 다른 솔로 운영자들이 해결하려 애쓸 문제를 이미 해결해둔 셈입니다.

## 한국 솔로 운영자 맥락에서 주의

**설계 없는 위임은 보트시팅이 됩니다.** Brockman의 비전에 흥분해서 Claude Code에게 모든 것을 위임해버리면, 다음 주에 Nathan Labenz의 6.4시간 통계가 대표님 달력에 재현됩니다. 솔로 운영자는 조직이 없으니 잘못된 AI 결과물이 대표님 브랜드에 직접 붙습니다. 분류 기준 없는 위임보다는 작게 시작하는 것이 안전합니다.

**"승인 피로"는 혼자 일할 때 더 빨리 옵니다.** 기업에서는 여러 명이 큐를 나눠보지만, 솔로 운영자는 혼자 다 봐야 합니다. 큐가 조금이라도 넘치면 "그냥 다 승인" 반사가 더 빨리 생깁니다. 따라서 큐 항목 수 상한선(예: 하루 최대 5건)을 시스템 설계에서 강제하는 것이 좋습니다.

## 더 깊이 보려면

- [Greg Brockman: Why Human Attention Is the New Bottleneck (YouTube / Sequoia AI Ascent 2026)](https://www.youtube.com/watch?v=bBS93A0BeNI)
- [Core Memory EP.67: The Great Reset at OpenAI — Sam Altman & Greg Brockman (2026)](https://www.corememory.com/p/the-great-reset-at-openai-ep-67-sam-altman-greg-brockman)
- [AI Agent Approval Workflows: Human Oversight That Scales (waxell.ai)](https://waxell.ai/blog/ai-agent-approval-workflows)
- [Human-in-the-Loop AI Agents: When Approvals Matter in 2026 (getclaw.sh)](https://getclaw.sh/blog/human-in-the-loop-ai-agents-approvals-2026)
- [Anthropic — How we contain Claude (engineering.anthropic.com)](https://www.anthropic.com/engineering/how-we-contain-claude)
- [AWS Agentic AI Lens: HITL for Critical Decisions (docs.aws.amazon.com)](https://docs.aws.amazon.com/wellarchirected/latest/agentic-ai-lens/agentsec04-bp02.html)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "에이전트에게 다 맡겼더니 오히려 더 바빠졌어요" — 대표님 주변 솔로프리너 10명 중 7명이 느끼는 감각입니다. 판단 큐가 없기 때문입니다.
- **숫자**: AI가 주당 13시간을 돌려줬는데, 판단 큐 설계가 없으면 6.4시간이 보트시팅으로 사라집니다. 판단 큐가 있으면 그 6.4시간도 회수할 수 있습니다.
- **삽질**: 모든 에이전트 행동에 승인을 요청했더니 하루에 40건의 알림이 쌓였고, 결국 전부 '자동 승인'하게 됐습니다. 감시 모델 붕괴. 이게 승인 피로입니다.
- **훅**: "Brockman이 '판단만 남겨라'고 했습니다. 그런데 그 판단을 담는 그릇, 판단 큐를 설계하지 않으면 어떻게 될까요? 수요일 데이터가 답합니다 — 주당 6.4시간이 '판단 아닌 판단'에 증발합니다."
