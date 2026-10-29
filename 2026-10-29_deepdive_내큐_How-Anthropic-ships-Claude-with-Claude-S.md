---
date: 2026-10-29
category: 내큐
subject: How Anthropic ships Claude with Claude: Separating the Brain from the Hands
source: Latent Space
sourceUrl: https://latent.space/p/opus55/
tags: [AI탐구, deepdive, 내큐]
starred: false
micro_action: Obsidian에서 'AI 에이전트 뇌-손 분리 아키텍처' 노트를 생성하고, 현재 비서앱/ERP 기능 중 '핵심 로직(뇌)'과 '외부 API 연동(손)'을 구분하는 아이디어 3가지 기록하기.
---

# 앤트로픽의 '뇌-손 분리' AI 에이전트 아키텍처 — 핵심 추론과 외부 도구 연동의 명확한 분리

> 출처: Latent Space · 원본: https://latent.space/p/opus55/

## 콘텐츠 핵심
**[원본 콘텐츠가 짧아 추정 분석이 들어감]**
이 콘텐츠는 앤트로픽(Anthropic)이 자사의 AI 모델인 Claude를 개발하고 배포하는 과정에서 채택한 '뇌(Brain)'와 '손(Hands)' 분리 아키텍처에 대해 다룹니다. '뇌'는 Claude 모델 자체의 핵심적인 추론 능력과 언어 이해 능력을 의미하며, 이는 외부 환경이나 도구에 의존하지 않는 순수한 지능 영역입니다. 반면 '손'은 이 '뇌'의 지시를 받아 외부 API, 데이터베이스, 파일 시스템 등 다양한 도구와 상호작용하며 실제 작업을 수행하는 에이전트 시스템을 지칭합니다. 이러한 분리 전략은 모델의 핵심 성능을 외부 복잡성으로부터 보호하면서도, 다양한 도구를 유연하게 활용하여 복잡한 현실 세계의 문제를 해결할 수 있도록 설계되었습니다. Opus 5.5는 이러한 Claude 플랫폼의 최신 버전으로, AI 에이전트 엔지니어링의 발전된 형태를 보여줍니다. 이 접근 방식은 AI 시스템의 확장성, 안정성, 그리고 유지보수성을 크게 향상시키는 데 기여합니다.

## 무엇이 특별한가
**[원본 콘텐츠가 짧아 추정 분석이 들어감]**

*   **명확한 역할 분담을 통한 복잡성 관리:** 앤트로픽의 '뇌-손 분리'는 AI 에이전트 개발의 고질적인 문제인 복잡성 관리에 대한 우아한 해법을 제시합니다. '뇌'는 오직 추론과 계획에 집중하고, '손'은 오직 실행과 도구 사용에 집중함으로써, 각 모듈의 책임이 명확해집니다. 이는 마치 인간의 두뇌가 명령을 내리고 손이 도구를 사용해 그 명령을 수행하는 방식과 유사하여, 시스템 전체의 디버깅과 확장을 훨씬 용이하게 만듭니다. 이 구조는 AI 시스템이 복잡한 다단계 작업을 수행할 때 발생할 수 있는 오류를 줄이고, 예측 가능성을 높이는 데 결정적인 역할을 합니다.

*   **AI 자체를 활용한 AI 개발 및 운영 (Self-Application):** 콘텐츠 제목("How Anthropic ships Claude with Claude")에서 암시하듯, 앤트로픽은 Claude를 개발하고 배포하는 과정 자체에 Claude를 활용하는 'AI 네이티브' 접근 방식을 채택했을 가능성이 높습니다. 이는 AI가 단순한 도구를 넘어, 개발 및 운영 프로세스의 핵심 주체로 자리매김했음을 의미합니다. '뇌-손 분리' 아키텍처는 이러한 자기 참조적(self-referential) 개발 환경을 가능하게 하는 기반이 됩니다. 예를 들어, Claude(뇌)가 새로운 기능 개발 계획을 세우고, 다른 Claude 에이전트(손)가 실제 코드를 생성하거나 테스트를 수행하는 방식으로 작동할 수 있습니다.

*   **확장성과 유연성을 극대화하는 아키텍처:** '뇌'와 '손'의 분리는 시스템의 확장성과 유연성을 극대화합니다. 새로운 외부 도구(예: 새로운 API, 데이터베이스)가 추가될 때, '손' 부분만 업데이트하거나 새로운 '손' 모듈을 추가하면 됩니다. '뇌'의 핵심 로직은 변경 없이 유지될 수 있습니다. 마찬가지로, '뇌'의 추론 능력을 개선할 때도 '손' 부분에 미치는 영향을 최소화할 수 있습니다. 이는 빠르게 변화하는 AI 생태계에서 새로운 기술이나 요구사항에 신속하게 대응할 수 있는 민첩한 개발 환경을 제공합니다.

*   **안정성과 신뢰성 향상:** '뇌'와 '손'이 분리되어 독립적으로 작동함으로써, 한쪽에서 문제가 발생하더라도 다른 쪽에 미치는 영향을 최소화할 수 있습니다. 예를 들어, 특정 외부 도구(손)에 문제가 생기더라도 '뇌'의 추론 능력 자체는 영향을 받지 않으며, 에이전트 시스템은 다른 '손'을 사용하거나 오류를 적절히 처리할 수 있습니다. 이는 AI 에이전트가 더 복잡하고 중요한 작업을 수행할 때 필수적인 안정성과 신뢰성을 확보하는 데 기여합니다.

## 와당탕/느린호밀 적용 포인트

**[원본 콘텐츠가 짧아 추정 분석이 들어감]**

**오늘 30분 (micro)**:
Obsidian에서 'AI 에이전트 뇌-손 분리 아키텍처' 노트를 생성하고, 현재 비서앱(hyein-daily)과 ERP(wadangtang-erp) 기능 중 '핵심 로직(뇌)'과 '외부 API 연동(손)'을 구분하는 아이디어 3가지 기록하기. (예: hyein-daily의 사용자 의도 파악(뇌) vs. Notion/Google Calendar API 호출(손)).

**이번 주 1-2시간 (mid)**:
hyein-daily의 새 알림 처리 로직에서, 사용자 입력 분석 및 알림 내용 생성(뇌)과 실제 알림 전송(손, 예: Slack API 호출, 이메일 발송)을 분리하는 간단한 함수 인터페이스 설계 및 프로토타입 코드 스니펫 작성. `brain_process_notification(user_input)` 함수가 구조화된 알림 데이터를 반환하고, `hand_send_notification(structured_data, channel)` 함수가 이를 받아 실제 전송을 담당하도록 구현.

```python
# 예시: hyein-daily 알림 처리 로직
class Brain:
    def process_notification_intent(self, user_input: str) -> dict:
        # 사용자 입력 분석, LLM 호출 등 핵심 로직 (뇌)
        # 예: "내일 오전 9시에 팀 미팅 알림 줘" -> {"time": "tomorrow 9 AM", "event": "Team Meeting", "channel": "slack"}
        print(f"[Brain] Processing: {user_input}")
        # 이 부분은 Claude Code로 구현될 수 있는 핵심 추론 로직
        return {"time": "tomorrow 9 AM", "event": "Team Meeting", "channel": "slack"}

class Hands:
    def send_slack_notification(self, data: dict):
        print(f"[Hands] Sending Slack notification: {data['event']} at {data['time']}")
        # 실제 Slack API 호출 로직
        pass

    def send_email_notification(self, data: dict):
        print(f"[Hands] Sending Email notification: {data['event']} at {data['time']}")
        # 실제 이메일 API 호출 로직
        pass

    def dispatch_