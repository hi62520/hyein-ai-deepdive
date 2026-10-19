---
date: 2026-10-20
category: AI네이티브회사
subject: Cohere × Aleph Alpha — 소버린AI 대서양횡단 전략
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱 결제/메모 화면에 "이 데이터는 외부 AI에 전송되지 않습니다" 한 줄 배지 추가하기
---

# Cohere × Aleph Alpha — 프론티어가 아닌 프라이버시가 해자다

## 누구/무엇인가

Cohere는 2019년 캐나다 토론토에서 아이단 고메즈(Aidan Gomez)가 공동 창업한 엔터프라이즈 AI 플랫폼 기업입니다. 고메즈는 구글 브레인 재직 시절 AI 역사를 바꾼 논문 "Attention Is All You Need"(2017)의 공동 저자였으며, 그 통찰을 스타트업으로 가져왔습니다. Cohere는 OpenAI나 Anthropic처럼 소비자를 향하지 않습니다. 처음부터 정부·금융·의료·방산 등 규제 산업의 **온프레미스·프라이빗 배포**를 겨냥했습니다.

2026년 현재 Cohere의 연간 반복 매출(ARR)은 외부 추산 수억 달러 수준이며, 놀라운 점은 **전체 수익의 약 85%가 프라이빗 배포에서 나온다**는 사실입니다. 클라우드 API를 주력으로 파는 경쟁사와 근본적으로 다른 사업 구조입니다. 2026년 4월 독일의 Aleph Alpha와 합병을 발표하고 9월 16일 최종 합의서에 서명, 역사상 첫 **환대서양 소버린 AI 기업** 탄생을 예고하고 있습니다. 합병 후 기업가치는 약 200억 달러($20B)로 추산됩니다.

---

## 무엇이 특별한가

### 1. "에어갭도 됩니다" — North 플랫폼의 배포 철학

Cohere의 엔터프라이즈 플랫폼 **North**는 단일 아키텍처로 네 가지 배포 형태를 지원합니다: 온프레미스, 프라이빗 클라우드, 하이브리드, 완전 에어갭(인터넷 차단). 서버 최소 스펙은 **GPU 2장**입니다. 대형 클라우드 계약 없이도 병원 한 층, 군 현장 데이터센터, 법원 내부망에서 돌아간다는 의미입니다.

2026년 7월 2일, 미국 방산 소프트웨어 기업 Second Front는 UAE 현장에서 Cohere North를 **컨테이너형 이동식 데이터센터**에 단 90분 만에 배포했습니다. 운반 가능한 Armada Galleon 랙에 모델을 올려 현장 투입한 것으로, 에지 AI 배포의 실전 가능성을 공개적으로 증명한 사례입니다.

### 2. Command A+ — 오픈웨이트로 뒤집은 판

2026년 5월 20일 출시한 **Command A+**는 2,180억(218B) 파라미터 MoE(Mixture of Experts) 모델이지만 실제 추론 시 활성화되는 파라미터는 250억(25B)에 불과합니다. 128K 컨텍스트를 지원하고 추론·비전·번역·툴 유스를 하나의 가중치 세트로 처리합니다. 가장 눈에 띄는 결정은 **Apache 2.0 라이선스**로 공개한 것입니다. 상업 사용 가능, 수정 가능, 재배포 가능 — OpenAI·Anthropic이 닫아놓은 문을 Cohere는 열었습니다. 기업이 모델을 내부 인프라에 복사하고, 파인튜닝하고, 재배포할 수 있는 법적 자유를 줬습니다.

> "We want enterprises to own their AI, not rent it."
> — Aidan Gomez, 인터뷰 다수에서 반복한 원칙

### 3. Aleph Alpha 합병 — 소버린 AI의 대서양 교두보

독일 하이델베르크 기반 Aleph Alpha는 유럽 규제 데이터 주권 요건(GDPR, EU AI Act)에 특화된 프라이빗 AI 기업입니다. Cohere가 이 회사와 합병하면 **북미 + 유럽 규제 시장**을 단일 플랫폼으로 커버하는 최초의 기업이 됩니다. 합병 구조는 Cohere 주주 90%, Aleph Alpha 주주 10% 지분으로 결합하고, Schwarz Group(독일 최대 유통기업, Lidl·Kaufland 모기업)이 €5억(약 5,400억 원)을 앵커 투자합니다. Aleph Alpha 공동 CEO 일한 세어(Ilhan Scheer)는 COO로, 공동 창업자 사무엘 바인바흐(Samuel Weinbach)는 최고연구책임자(CRO)로 합류 예정입니다. 합병은 2026년 말 규제 승인 완료가 목표입니다.

### 4. 버티컬 전략 — "North for Pharma"

2026년 5월 Cohere는 바이오파마·헬스케어 특화 AI 스타트업 **Reliant AI**를 인수해 "North for Pharma" 버티컬을 만들었습니다. 임상 데이터, 약물 안전성 보고서, 규제 문서를 사내에서만 처리하는 파이프라인입니다. 같은 달 SAP과 EU AI Cloud 파트너십을 발표, SAP BTP 안에 North 플랫폼을 임베드하는 계약도 체결했습니다. Carahsoft와는 2026년 7월 미국 연방정부 조달 계약을 통한 공공 섹터 배포 협약을 맺었습니다. 단일 모델을 수평으로 파는 것이 아니라, 규제 산업별로 수직 통합하는 전략입니다.

### 5. 소버린 AI 수요 데이터

Cohere가 의뢰하고 IDC가 수행한 2026년 설문(미국·캐나다·영국·독일 대형 기업 500개 이상 AI 의사결정자)에서 규제 업종의 최대 AI 도입 장벽 1위는 **데이터 유출·프라이버시·컴플라이언스 리스크**였습니다. OpenAI의 ChatGPT Enterprise나 Anthropic의 Claude for Work도 이 우려를 완전히 해소하지 못합니다 — 계약서상 데이터를 학습에 쓰지 않는다고 해도, 클라우드 엔드포인트로 데이터가 나가는 구조 자체를 거부하는 고객이 많기 때문입니다.

---

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱의 결제 내역 또는 메모 입력 화면에 **"이 데이터는 외부 AI 서버에 전송되지 않습니다"** (또는 반대로 "AI 처리 시 Anthropic API로 전송됩니다") 한 줄 배지를 추가하세요. 고객 신뢰 UX의 첫 단계입니다.

**이번 주 1-2시간 (mid)**: 와당탕 비서앱의 각 기능별로 **데이터 흐름 지도**를 만들어 보세요. "외부 전송 없음 / Anthropic API 전송 / 제3자 전송" 세 등급으로 분류하고, 고객이 볼 수 있는 간단한 개인정보 처리 방침 페이지(1페이지)로 만드는 것이 목표입니다. 코드 예시:

```markdown
## 와당탕 AI 데이터 처리 등급

| 기능 | 처리 위치 | 외부 전송 |
|------|-----------|-----------|
| 공구 메모 저장 | 자체 DB | 없음 |
| AI 캡션 생성 | Anthropic API | 내용 전송됨 |
| 매출 집계 | 자체 DB | 없음 |
```

**이번 달 실험 (macro)**: ERP의 민감 데이터(매출·거래처 정보)를 AI에 전송하지 않고도 인사이트를 뽑는 **로컬 집계 레이어**를 설계해 보세요. 예를 들어 매출 원본 대신 집계값만 AI에게 넘기는 방식입니다. 측정 지표: 고객 문의 중 "내 데이터 어디 가요?" 빈도 변화.

---

## 한국 솔로 운영자 맥락에서 주의

**Cohere 전략을 그대로 따라 하면 안 되는 이유**: Cohere의 온프레미스 전략은 수백만 달러짜리 엔터프라이즈 계약을 전제로 합니다. 와당탕·느린호밀처럼 1인 사업자가 직접 GPU 서버를 마련해 운영하면 비용 대비 효과가 나오지 않습니다. 핵심 교훈은 **인프라가 아니라 신뢰 포지셔닝**입니다 — "우리 서비스는 고객 데이터를 어떻게 다루는가"를 명확히 말하는 것만으로도 규제 업종 고객(병원, 변호사, 세무사)에게 큰 차별점이 됩니다.

또 Cohere의 Apache 2.0 공개 전략은 개발자 생태계가 클 때 효과가 납니다. 와당탕의 현재 단계에서는 모델 공개보다 **고객 인터뷰를 공개**하는 것이 더 강력한 신뢰 자산입니다.

---

## 더 깊이 보려면

- [Cohere 공식 블로그](https://cohere.com/blog)
- [Cohere + Aleph Alpha 합병 발표 (BNN Bloomberg)](https://www.bnnbloomberg.ca/business/2026/04/24/canadian-ai-firm-cohere-to-merge-with-german-company-aleph-alpha/)
- [Second Front × Cohere UAE 에지 배포 (Las Vegas Sun)](https://lasvegassun.com/news/2026/jul/02/second-front-and-cohere-successfully-deploy-sovere/)
- [SiliconAngle — Cohere & Aleph Alpha 최종 합의](https://siliconangle.com/2026/09/16/cohere-and-aleph-alpha-agree-to-merge-in-reported-20b-deal/)
- [The State of Sovereign AI Adoption 2026 (IDC/Cohere 요약)](https://www.plushcap.com/content/cohere/blog/cohere-the-state-of-sovereign-ai-adoption-in-2026)

---

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "ChatGPT에 회사 문서 넣으면 학습에 쓰인다는 소문이 있어서 못 쓰겠어요" — 규제 업종 고객의 가장 흔한 불안. Cohere는 이 불안을 제품으로 만들었습니다.
- **숫자**: Cohere 수익의 **85%가 프라이빗 배포**. OpenAI가 API 과금으로 돈 버는 동안, Cohere는 기업의 서버실 안에서 돈 벌고 있습니다.
- **숫자**: UAE 에지 현장 배포 **90분**. GPU 2장짜리 이동식 서버에서 엔터프라이즈 AI가 돌아간다.
- **숫자**: Cohere + Aleph Alpha 합병 후 추산 기업가치 **$20B(약 28조 원)**, Schwarz Group 앵커 투자 **€5억**.
- **삽질**: Cohere는 초기에 검색·임베딩으로 포지셔닝했다가 2023년 Command R 출시로 에이전트·RAG 쪽으로 방향을 틀었습니다. "프론티어 모델 경쟁에서 이기려 했다면 망했을 것"이라는 뒤늦은 고백이 여러 인터뷰에 등장합니다.
- **훅**: "ChatGPT가 금지된 산업이 있습니다. 병원, 군, 법원, 법무팀 — 그곳의 AI 예산은 누가 먹을까요?"
