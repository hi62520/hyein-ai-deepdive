---
date: 2026-06-23
category: AI네이티브회사
subject: Meta Llama 4 — 오픈소스가 플랫폼이 될 때 해자가 만들어진다
tags: [AI탐구, deepdive]
starred: false
micro_action: 옵시디언에 "Llama 4 Scout API 테스트" 노트 생성 후, Together AI 또는 Groq에서 API 키 발급 받아 10M 컨텍스트로 최근 비서앱 로그 한 달치를 한 번에 요약하는 프롬프트 실행
---

# Meta Llama 4 — 오픈소스가 플랫폼이 될 때 해자가 만들어진다

## 누구/무엇인가

Meta(구 Facebook)는 2026년 4월, 인류 역사상 가장 강력한 오픈소스 AI 모델군인 **Llama 4 Herd**를 공개했습니다. Llama 4 Scout, Maverick, Behemoth 세 가지 변형으로 구성된 이 모델군은 처음으로 **MoE(Mixture of Experts) 아키텍처**와 **네이티브 멀티모달 능력**을 오픈웨이트로 결합한 사례입니다. Scout는 1,700만 개의 활성 파라미터에 10M(천만) 토큰 컨텍스트 윈도우를 탑재했고, Maverick은 128개 전문가 모듈로 GPT-4o와 Gemini 2.0 Flash를 공개 벤치마크에서 앞질렀습니다. Behemoth는 2,880억 개의 활성 파라미터를 가진 역대 최대 모델로 현재 학습 중입니다. 같은 달 Meta는 **Meta Superintelligence Labs(MSL)**를 설립하고, 첫 독점 프론티어 모델인 Muse Spark를 API 전용으로 출시하며 완전히 새로운 단계에 진입했습니다. 2026년 CapEx만 최대 1,350억 달러를 예고한 이 회사는, AI를 제품이 아닌 플랫폼으로 바라보고 있습니다.

## 무엇이 특별한가

**1. 10M 컨텍스트 윈도우 — 현존 최장의 오픈소스 기억**

Llama 4 Scout의 컨텍스트 윈도우는 1,000만 토큰으로, 경쟁 오픈소스 모델 대비 약 10배 깁니다. 이는 개발 코드베이스 전체, 한 달치 고객 응대 로그, 혹은 수백 개의 PDF 문서를 **한 번의 프롬프트**로 처리할 수 있다는 의미입니다. 비용은 입력 1M 토큰당 $0.08, 출력 $0.30으로, 유사 성능의 Claude 또는 GPT-4o 계열 대비 10분의 1 수준입니다. 솔로 운영자가 에이전트를 돌릴 때 가장 무서운 것은 토큰 비용인데, Scout는 그 공포를 구조적으로 제거합니다.

**2. 저커버그의 AI-Native 전환 — "CEO 에이전트"까지 만들었다**

2026년 초 저커버그는 자신의 업무를 보조하는 **AI CEO 에이전트**를 직접 구축·운용 중이라고 밝혔습니다. 이 에이전트는 Meta 전 제품 포트폴리오에서 실시간으로 데이터를 수집하고 의사결정을 지원하며, 기존 인간 관료주의 계층을 우회합니다. 더 나아가 Meta는 2026년 상반기 목표로 **엔지니어의 65%가 커밋 코드의 75% 이상을 AI로 작성**하는 기준을 내부에 설정했습니다. 8,000명을 감원하고 7,000명을 AI 워크플로우 부서로 재배치한 것은 이 전환의 물리적 증거입니다. "Superintelligence is coming into sight. I am fully committed to doing what it takes for Meta to lead the way." — 저커버그의 선언은 수사가 아닌 행동으로 뒷받침됩니다.

**3. 플랫폼 전략으로서의 오픈소스 — 1.3조짜리 무료 선물의 진짜 이유**

Meta가 Llama를 무료로 공개하는 것은 자선이 아닙니다. Llama가 업계 표준 인터페이스가 되면, 개발자들이 Meta 생태계 위에서 앱과 에이전트를 쌓고, 그 트래픽이 Meta의 광고 인프라와 데이터로 돌아옵니다. OpenAI SDK 호환 Llama API를 출시한 이유도 마찬가지입니다 — 개발자가 API 키 하나로 ChatGPT에서 Llama로 전환할 장벽을 0으로 낮춥니다. Meta의 오픈소스 전략은 **플랫폼 플레이북**이지, 기술 공유 정신이 아닙니다.

**4. Llama 4 Maverick — $0.27/$0.85로 GPT-4o를 이긴 모델**

Maverick은 입력 $0.27, 출력 $0.85 (1M 토큰 기준)로 GPT-4o 대비 약 5-7배 저렴하면서 멀티모달 벤치마크에서 앞서는 결과를 보였습니다. AWS Bedrock에서도 Llama 3.1 405B($5.32) 대비 약 90% 저렴하게 Maverick을 쓸 수 있습니다. Groq, Together AI, Fireworks 등 서드파티 추론 제공자를 통하면 1M 토큰에 $0.05~$0.90 범위로 훨씬 저렴하게 접근 가능합니다. **성능은 최상위, 비용은 저예산** — 솔로 개발자에게 이보다 유리한 조건은 없습니다.

**5. LlamaFirewall·Llama Guard 4 — 보안 스택까지 오픈소스로**

Meta는 LlamaCon에서 Llama Guard 4(콘텐츠 모더레이션), Prompt Guard 2(프롬프트 인젝션 방지), LlamaFirewall(통합 보안 오케스트레이터)을 오픈소스로 공개했습니다. 에이전트를 만들 때 보안 레이어 구축 비용이 0에 수렴한다는 의미입니다. 에이전트 보안을 클로드 API 필터에만 맡기던 솔로 개발자라면, 이 도구들을 ERP 에이전트 파이프라인에 삽입해 자체 가드레일을 구성할 수 있습니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 옵시디언에 "Llama 4 Scout API 테스트" 노트를 생성하고, Groq 또는 Together AI에서 무료 API 키를 발급받아 비서앱의 최근 1개월치 로그를 10M 컨텍스트 프롬프트로 한 번에 요약해 봅니다. Claude API 호출 1회 비용과 비교해 기록해 두세요.

**이번 주 1-2시간 (mid)**: ERP의 주문·재고 데이터를 Llama 4 Scout로 처리하는 "저비용 분석 에이전트" 프로토타입 구현. Claude는 창의적 생성 및 고객 대면 작업, Llama Scout는 대규모 내부 데이터 파싱·집계에 배치하는 **하이브리드 라우팅** 패턴을 적용합니다.

```python
# 비서앱/ERP 라우팅 패턴 스케치
def route_request(task_type: str, context_length: int):
    if task_type == "customer_facing" or task_type == "creative":
        return "claude-sonnet-4-6"  # 품질 우선
    elif context_length > 100_000 or task_type == "internal_analysis":
        return "llama-4-scout"      # 비용 + 컨텍스트 우선
    else:
        return "llama-4-maverick"   # 범용 저비용
```

**이번 달 실험 (macro)**: 비서앱의 내부 로그 분석, ERP 데이터 집계, 반복 보고서 생성 3가지 작업을 Llama 4로 전환하고 Claude API 비용과 비교 측정. 목표 지표: 월 API 비용 30% 이상 절감, 응답 품질 유지 여부(사용자 평점 또는 자동 평가).

## 한국 솔로 운영자 맥락에서 주의

**1. 오픈소스 = 셀프 호스팅 부담**이라는 착각을 조심해야 합니다. Llama 4 Maverick을 직접 운영하려면 H100 8장 규모의 GPU가 필요합니다. 와당탕·느린호밀 규모에서 직접 호스팅은 비현실적이며, Groq·Together AI·AWS Bedrock 등의 관리형 API를 쓰는 것이 현명합니다. "오픈소스니까 무료"라는 오해가 시간 낭비를 낳습니다.

**2. Meta의 라이선스 조건을 반드시 확인**하세요. Llama 4는 "오픈소스"이지만 월간 활성 사용자 7억 명 초과 서비스에는 별도 라이선스가 필요합니다. 현재 와당탕·느린호밀 규모에서는 전혀 문제 없지만, 강의 플랫폼 수강생 수가 급성장할 경우 이 조건을 미리 인지해 두어야 합니다.

## 더 깊이 보려면

- [Llama 4 공식 발표 — Meta AI Blog](https://ai.meta.com/blog/llama-4-multimodal-intelligence/)
- [Zuckerberg AI CEO Agent 보도 — eWeek](https://www.eweek.com/news/mark-zuckerberg-ai-agent-meta/)
- [Meta AI-Native 전환 — Breitbart Tech](https://www.breitbart.com/tech/2026/03/27/mark-zuckerbergs-meta-pushes-to-become-an-ai-native-company/)
- [Llama 4 비용 비교 — AI Cost Check](https://aicostcheck.com/blog/meta-llama-pricing-guide-2026)
- [Meta Superintelligence Labs — Built In](https://builtin.com/artificial-intelligence/meta-superintelligence-labs)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: Claude API 비용이 월 30만 원을 넘어가는 순간, 솔로 운영자는 "이게 지속 가능한가?"를 묻게 됩니다. Llama 4는 그 질문에 대한 구조적 대안입니다.
- **숫자**: Scout 10M 토큰 컨텍스트 = A4 용지 약 7,500장 분량. ERP 로그 1년치를 한 번에 넣고 패턴 분석 가능.
- **삽질**: Meta 내부에서 AI Second Brain(Anthropic Claude 인프라 기반)을 단 한 명의 직원이 만들어 전사 도구가 됐습니다. 솔로도 사내 도구를 만든다는 발상이 가능합니다.
- **훅**: "세계에서 가장 비싼 회사가 AI를 왜 무료로 풀까요? 그 답이 당신의 사업 모델에도 적용됩니다."
