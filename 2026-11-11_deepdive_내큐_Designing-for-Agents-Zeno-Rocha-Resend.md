---
date: 2026-11-11
category: 내큐
subject: AI 에이전트를 위한 API 디자인: AEO를 넘어 Agent Experience로
source: Latent Space
sourceUrl: https://latent.space/p/resend/
tags: [AI탐구, deepdive, 내큐]
starred: false
micro_action: hyein-daily /study에 'AI 에이전트 친화적 API 문서 가이드' 관련 리소스 검색 및 1개 북마크 추가
---

# AI 에이전트를 위한 API 디자인: AEO를 넘어 Agent Experience로 — AI가 스스로 최적의 도구를 선택하고 사용하게 만드는 방법

> 출처: Latent Space · 원본: https://latent.space/p/resend/

## 콘텐츠 핵심
이 콘텐츠는 Answer Engine Optimization (AEO)의 개념이 끝나는 지점과 Agent Experience가 시작되는 지점에 대한 중요한 질문을 던집니다. (원본 콘텐츠가 짧아 추정 분석이 들어감) Resend의 Zeno Rocha는 이메일 API 서비스인 Resend의 사례를 통해, AI 에이전트인 Claude Code가 어떻게 이메일 API를 '선택'하고 '사용'하는지에 초점을 맞춥니다. 이는 단순히 인간 사용자가 검색 엔진에서 정보를 찾는 것을 넘어, AI 에이전트가 특정 작업을 수행하기 위해 필요한 최적의 도구(API)를 스스로 식별하고 통합하는 환경을 설계하는 것의 중요성을 강조합니다. 즉, AI가 단순히 정보를 찾아주는 것을 넘어, '행동'하고 '결정'하는 주체가 될 때, 그들을 위한 문서와 시스템은 어떻게 달라져야 하는지에 대한 통찰을 제공합니다.

## 무엇이 특별한가
이 짧은 콘텐츠는 AI 네이티브 시대의 핵심적인 패러다임 전환을 시사하며, 다음과 같은 점에서 특별합니다.

*   **인간 중심에서 에이전트 중심 디자인으로의 전환**: 대부분의 API 문서와 시스템은 여전히 인간 개발자가 읽고 이해하며 통합하는 것을 전제로 설계됩니다. 이 콘텐츠는 AI 에이전트, 특히 Claude Code와 같은 코딩 에이전트가 API의 '주요 사용자'가 될 수 있음을 암시하며, 이들이 API를 스스로 탐색하고 선택하며 호출할 수 있도록 시스템과 문서를 설계해야 한다는 새로운 관점을 제시합니다. 이는 단순히 "AI가 내 문서를 이해하게 만들자"를 넘어 "AI가 내 문서를 기반으로 행동하게 만들자"는 사고의 전환입니다.

*   **AEO와 Agent Experience의 명확한 구분**: Answer Engine Optimization (AEO)은 AI 기반 검색 엔진이 질문에 대한 최적의 답변을 찾아 사용자에게 제공하도록 콘텐츠를 최적화하는 데 중점을 둡니다. 하지만 이 콘텐츠는 AEO가 끝나는 지점에서 Agent Experience가 시작된다고 말하며, AI가 단순히 '정보를 찾는' 것을 넘어 '특정 작업을 수행하기 위해 도구를 선택하고 사용하는' 단계로 나아갈 때 필요한 새로운 최적화 영역을 정의합니다. 이는 AI가 단순한 정보 소비자를 넘어 능동적인 행위자가 될 때, 우리가 고려해야 할 시스템 디자인의 깊이가 달라짐을 보여줍니다.

*   **Claude Code를 구체적인 사용자 페르소나로 설정**: 단순히 'AI 에이전트'라고 추상적으로 언급하는 대신, 'Claude Code'라는 특정 코딩 에이전트를 명시적으로 언급함으로써, 이 개념이 매우 구체적이고 실용적인 문제임을 보여줍니다. Claude Code는 API 명세, 인증 방식, 에러 처리 등을 이해하고 실제 코드를 생성하여 API를 호출해야 하므로, 그를 위한 문서는 단순히 기능 설명을 넘어 API의 구조적 특징과 사용 패턴을 명확하게 전달해야 한다는 점을 강조합니다. Resend가 이러한 관점에서 내부 시스템이나 문서를 구축하고 있다는 점은 선도적인 접근 방식입니다.

## 와당탕/느린호밀 적용 포인트

### 오늘 30분 (micro)
hyein-daily /study에 'AI 에이전트 친화적 API 문서 가이드' 관련 리소스 검색 및 1개 북마크 추가

### 이번 주 1-2시간 (mid)
`wadangtang-erp` 내 `hyein-agent` 모듈에 새로운 `AgentTool` (예: `EmailSenderTool`)을 추가하고, 이 도구가 Resend API (혹은 다른 이메일 API)를 호출하도록 스켈레톤 코드 작성. 이때, Claude Code가 이 `AgentTool`의 기능과 사용법을 쉽게 이해할 수 있도록 `tool_description`을 상세하게 작성하는 데 집중합니다.

```python
# wadangtang-erp/hyein-agent/tools/email_sender_tool.py (예시)
from langchain_core.tools import BaseTool
import requests

class EmailSenderTool(BaseTool):
    name = "email_sender"
    description = (
        "이메일을 발송하는 도구입니다. "
        "수신자 이메일 주소(recipient_email), 제목(subject), 본문(body)을 필수로 받습니다. "
        "HTML 형식의 이메일도 지원하며, 'is_html'을 True로 설정할 수 있습니다. "
        "이 도구는 Resend API를 사용하여 안정적으로 이메일을 보냅니다. "
        "사용 예시: email_sender(recipient_email='test@example.com', subject='회의 알림', body='내일 10시 회의입니다.')"
    )

    def _run(self, recipient_email: str, subject: str, body: str, is_html: bool = False) -> str:
        # 여기에 Resend API 호출 로직 구현
        # API 키는 환경 변수에서 가져오거나 안전하게 관리
        # 예:
        # headers = {"Authorization": f"Bearer {RESEND_API_KEY}"}
        # payload = {
        #     "from": "onboarding@resend.dev", # 발신자 이메일 (Resend에 등록된 도메인)
        #     "to": [recipient_email],
        #     "subject": subject,
        #     "html": body if is_html else None,
        #     "text": body if not is_html else None,
        # }
        # response = requests.post("https://api.resend.com/emails", headers=headers, json=payload)
        # if response.status_code == 200:
        #     return f"이메일이 성공적으로 발송되었습니다: {response.json().get('id')}"
        # else:
        #     return f"이메일 발송 실패: {response.status_code} - {response.text}"
        return f"이메일 발송 기능 스켈레톤 구현 완료. 수신자: {recipient_email}, 제목: {subject}"

    async def _arun(self, recipient_email: str, subject: str, body: str, is_html: bool = False) -> str:
        raise NotImplementedError("Async operation not supported yet.")

# 이 Tool을 hyein-agent의 Tool 목록에 추가하여 Claude Code가 사용할 수 있도록 설정
```

### 이번 달 실험 (macro)
`느린호밀` 강의 콘텐츠 제작 과정에서 AI 에이전트가 외부 자료(논문, 기사, 블로그)를 *선택*하고 *요약*하는 파일럿 시스템을 구축합니다. 이 시스템은 Claude Code에게 특정 주제에 대한 자료를 찾고 요약하도록 지시했을 때, AI가 어떤 웹 스크래핑/검색 API를 선택하고(예: SerpAPI, ScrapeOps), 해당 API의 문서(Tool Description)를 얼마나 정확하게 해석하여 필요한 정보를 추출하는지 측정합니다. 성공 기준은 "AI가 3가지 다른 주제에 대해 각각 5개 이상의 관련 자료를 찾아내고, 각 자료의 핵심 내용을 3문장 이내로 요약하는 데 80% 이상의 정확도를 달성"하는 것으로 설정합니다.

## 한국 솔로 운영자 맥락에서 주의
이 콘텐츠의 아이디어를 한국 솔로 운영자 맥락에서 적용할 때 몇 가지 주의할 점이 있습니다.

*   **한국어 API 문서 및 에이전트 친화성 부족**: Resend와 같은 글로벌 서비스는 영어권 개발자를 위한 에이전트 친화적 문서화에 투자할 여력이 크지만, 한국의 많은 SaaS 및 API 서비스는 아직 인간 개발자 중심의 문서화에 머물러 있습니다. Claude Code가 '선택'할 수 있는 고품질의 한국어 API 문서나, 에이전트가 직접 파싱하고 이해하기 쉬운 구조화된 API 명세(OpenAPI/Swagger 등)가 부족할 수 있습니다. 따라서 AI 에이전트가 사용할 한국어 API를 찾거나, 기존 한국어 API 문서를 에이전트 친화적으로 변환하는 추가적인 작업이 필요할 수 있습니다.

*   **솔로프레너의 리소스 제약과 점진적 접근**: 대규모 조직이 아닌 1인 운영자는 '에이전트 친화적' 시스템을 처음부터 구축하는 데 시간, 비용, 인력 측면에서 큰 제약이 있습니다. 모든 시스템을 한 번에 에이전트 중심으로 전환하기보다는, 현재 가장 반복적이고 AI가 개입했을 때 효율이 극대화될 수 있는 특정 워크플로우(예: 이메일 발송, 자료 검색 및 요약, 일정 관리)부터 시작하여 점진적으로 에이전트 친화적인 도구와 문서를 구축해 나가는 전략이 현실적입니다.

## 더 깊이 보려면
- [원본: Designing for Agents — Zeno Rocha, Resend](https://latent.space/p/resend/)
- [OpenAPI Specification (Swagger)](https://swagger.io/specification/) - AI 에이전트가 API를 이해하고 사용할 수 있도록 돕는 표준 명세
- [LangChain Tools Documentation](https://python.langchain.com/docs/modules/agents/tools/) - AI 에이전트가 외부 도구를