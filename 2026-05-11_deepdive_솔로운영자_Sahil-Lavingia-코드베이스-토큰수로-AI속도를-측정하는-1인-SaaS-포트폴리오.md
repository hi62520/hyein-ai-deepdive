---
date: 2026-05-11
category: 솔로운영자
subject: Sahil Lavingia — 코드베이스 토큰 수로 AI 속도를 측정하는 1인 SaaS 포트폴리오
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱/ERP 코드 디렉터리에서 `wc -w $(find . -name "*.py" -o -name "*.js" -o -name "*.ts" | head -100)` 실행 후 "AI가 혼자 커버할 수 있는 파일 vs 못하는 파일" 경계를 메모로 남기기
---

# Sahil Lavingia — 코드베이스 토큰 수로 AI 속도를 측정하는 1인 SaaS 포트폴리오

## 누구/무엇인가

Sahil Lavingia는 2011년 Pinterest 두 번째 직원 출신으로 Gumroad를 창업한 솔로프레너입니다. 한때 100명 가까운 팀과 VC 펀딩을 등에 업고 달렸지만, 2015년 Series B 실패 이후 팀을 5명으로 줄이고 수익 중심 운영으로 전환했습니다. 지금 Gumroad는 연 매출 $10–20M(약 130–260억 원), 기업가치 $100M 수준이며, 정규직 직원은 사실상 Sahil 본인 한 명입니다. 그는 여기서 멈추지 않고 "Antiwork"라는 브랜드 아래 Flexile(캡 테이블 관리), Helper(AI 고객지원), Iffy(콘텐츠 모더레이션), Shortest(테스트 자동화) 등 소규모 SaaS 5개를 동시에 운영합니다. 2025년 초에는 미국 재무부 산하 DOGE의 VA(보훈부) 소속 소프트웨어 엔지니어로 55일간 일하며 정부 시스템에 AI 코딩 도구(OpenHands)를 적용하려 시도했다가 Fast Company 인터뷰가 공개된 직후 해고되기도 했습니다.

---

## 무엇이 특별한가

### 1. "코드베이스 토큰 수"라는 AI 속도 지표

Sahil이 2025년 초 X(트위터)에 올린 한 트윗이 개발자 커뮤니티를 뒤흔들었습니다.

> "No longer hiring junior or even mid-level software engineers."
> ("주니어는 물론 미드레벨 소프트웨어 엔지니어도 더 이상 채용하지 않는다.")

그는 각 코드베이스의 **토큰 수(tokens per codebase)**를 공개했습니다.

| 제품 | 토큰 수 |
|---|---|
| Gumroad | 2,000,000 |
| Flexile | 800,000 |
| Helper | 500,000 |
| Iffy | 200,000 |
| Shortest | 100,000 |

당시 Claude 3.5 Sonnet과 o3-mini의 컨텍스트 윈도우가 200K였으므로, **Iffy와 Shortest는 AI가 컨텍스트를 전부 읽고 100% 단독 작성이 가능**합니다. Gumroad와 Flexile은 아직 인간 판단이 필요하지만, 2026년 말까지 모든 코드베이스를 AI가 작성하는 것이 목표입니다. "코드베이스 크기 = AI 자율성 한계"라는 등식이 실무 지표로 등장한 것입니다.

### 2. 현재 AI 코드 작성 비율 41%, 목표 80%

2025년 기준 Gumroad 전체 코드 커밋의 **41%를 AI 에이전트(주로 Devin)가 작성**합니다. Devin은 anti-work/gumroad, antiwork/flexile, antiwork/gum.new 등 레포에서 **1,583개 PR을 머지**했습니다. Sahil의 목표는 2026년 말까지 이 비율을 **80%**로 끌어올리는 것입니다.

생산성 향상 수치도 구체적입니다. Lenny Rachitsky 팟캐스트(2025년 4월)에서 밝힌 바에 따르면, 예전에 2주 걸리던 기능을 지금은 **2시간**에 구현합니다. 정확히는 **40배 생산성 향상**입니다. 작은 기능 요청은 Slack 스레드에서 Devin에게 바로 지시해 **10분 안에 프로덕션**으로 나갑니다.

### 3. 3단계 AI 개발 워크플로

Sahil의 실제 작업 순서는 다음과 같습니다.

1. **기획 단계** — Deep Research와 대화해 사양(spec) 초안 작성. PRD 대신 AI에게 "뭘 만들지"를 말로 설명.
2. **프로토타입 단계** — v0에 프롬프트 입력 → UI 시제품 즉시 생성. "PRD에서 놓쳤을 세부사항을 UI 설계 단계에서 잡아낸다"고 강조.
3. **구현 단계** — Devin에게 v0 프로토타입을 전달 → 실제 코드 작성 → PR 자동 생성 → QA 후 머지 → 배포.

특히 그는 **"코드베이스 아키텍처가 AI 속도를 결정한다"**고 강조합니다. Flexile에는 CSS 파일이 단 하나(181줄 테마 파일)뿐입니다. 코드가 지저분하면 AI가 혼란을 일으켜 생산성이 급락하기 때문입니다.

### 4. $33,000 AI 생산성 바운티

Sahil은 팀원(주로 계약직)에게 독특한 인센티브를 제공합니다. **"v0·Cursor·Devin을 사용해 CEO인 나보다 더 빨리 기능을 출시하면 $33,000을 준다"**는 바운티입니다. AI 도입 의지 없는 엔지니어를 걸러내고, 진짜 AI-native 개발자를 유인하는 장치입니다.

### 5. 수익 기반 로열티 펀딩 모델

전통 VC 방식(지분 투자 → 대규모 엑시트)이 AI 시대 솔로 창업자에게 맞지 않는다고 판단한 Sahil은 **로열티 기반 펀딩(royalty-based funding)**을 실험합니다. 창업자에게 투자하되 미래 수익의 일정 비율을 돌려받는 방식으로, 대규모 엑시트 압박 없이 수익 중심 운영을 유지할 수 있습니다. Gumroad 자체도 이 구조와 유사한 방식으로 운영되고 있습니다.

---

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**:
비서앱 또는 ERP 코드 디렉터리에서 파일별 토큰(단어 수)을 측정해보세요. `wc -w $(find . -name "*.py" -o -name "*.js" -o -name "*.ts" | head -100)` 실행 후, "Claude가 단독으로 커버할 수 있는 파일(작은 것)"과 "인간 판단이 필요한 파일(큰 것)"을 구분해 옵시디언에 메모로 남겨 두세요. 이것이 대표님만의 "AI 자율성 지도"가 됩니다.

**이번 주 1-2시간 (mid)**:
비서앱의 새 기능 하나를 **Sahil 3단계 워크플로**로 실험해보세요.
1. Claude에게 "이 기능 왜 만드나, 어떤 화면이어야 하나" 말로 설명 → spec 초안 받기
2. v0(또는 Claude Artifacts)에 UI 프롬프트 입력 → 화면 초안 생성
3. 초안을 Claude Code에 붙여넣고 "이대로 구현해줘" → PR 작성 or 직접 구현

```bash
# 예시: 코드베이스 토큰 감지 스크립트 (Python)
import os, glob

total = 0
file_list = []
for f in glob.glob("**/*.py", recursive=True) + glob.glob("**/*.ts", recursive=True):
    words = len(open(f, encoding='utf-8', errors='ignore').read().split())
    file_list.append((f, words))
    total += words

file_list.sort(key=lambda x: x[1], reverse=True)
for f, w in file_list[:15]:
    print(f"{w:>8,}  {f}")
print(f"\n총 추정 토큰: {total:,}")
```

**이번 달 실험 (macro)**:
ERP 기능 중 가장 작고(토큰 적고) 독립적인 모듈 하나를 골라 **AI 단독 작성 → 인간 리뷰 → 배포** 사이클을 한 번 돌려보세요. 측정 지표: ① 기획~배포까지 실제 소요 시간, ② AI가 작성한 코드 비율, ③ 수정 횟수. 목표: 기존 대비 50% 이상 시간 단축.

---

## 한국 솔로 운영자 맥락에서 주의

**서비스 공개 투명성의 양날**:  
Sahil은 DOGE 경험을 Fast Company에 솔직하게 털어놨다가 55일 만에 해고됐습니다. 그는 Gumroad 수익·매출·팀 구조를 모두 공개하는 것으로도 유명합니다. 대표님의 와당탕연구소나 느린호밀에서 AI 운영 현황을 외부에 공유할 때는 "투명성"과 "경쟁 노출" 사이 균형을 의식적으로 조율해야 합니다. 한국 B2B 시장은 내부 운영 방식 노출에 훨씬 보수적인 편입니다.

**코드베이스 크기 = 혼자 감당할 수 있는가**:  
Sahil은 5개 제품을 동시 운영하지만 모두 토큰 수가 작습니다. 만약 ERP·비서앱이 계속 커져 2M 토큰을 넘으면, AI 에이전트가 전체 컨텍스트를 잡지 못해 버그가 늘어납니다. "기능을 추가하는 것"과 "코드베이스를 AI가 다룰 수 있는 크기로 유지하는 것"이 서로 긴장 관계에 있음을 Sahil 사례가 잘 보여줍니다.

---

## 더 깊이 보려면

- [Lenny's Podcast — Gumroad CEO's playbook to 40x his team's productivity](https://www.lennysnewsletter.com/p/gumroad-ceos-playbook-to-40x-his) (2025.04.22, 45분)
- [Sahil의 X 트윗 — "No longer hiring junior engineers"](https://x.com/shl/status/1887484068075274347)
- [Gumroad 2026 Annual Meeting — YouTube](https://www.youtube.com/watch?v=ffkECKX-WgU)
- [Tedium — Gumroad's Open-Source Play](https://tedium.co/2025/04/06/gumroad-open-source-doge-drama/)
- [TechCrunch — Sahil Lavingia DOGE 55일 후 퇴출](https://techcrunch.com/2025/05/28/founder-sahil-lavingia-says-he-was-booted-from-doge-after-just-55-days/)

---

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "코드가 커질수록 AI가 더 자주 틀린다. 그게 무서워서 기능을 못 추가하게 됐다." — AI 에이전트를 믿고 싶은데 코드베이스 자체가 걸림돌인 솔로 창업자의 딜레마.
- **숫자**: Gumroad 코드 커밋의 41%가 AI 작성 (2025 기준). 목표 80%. 2주 → 2시간, 40배 속도 향상. Devin이 머지한 PR만 1,583개.
- **삽질**: DOGE에 들어가 "정부 시스템에도 AI를 적용하면 되겠지"라 생각했다가 473,000명 조직의 인사 규칙에 막혀 55일 만에 퇴출. 기술 속도와 조직 정치 속도는 다르다.
- **훅**: "직원 없이 연 200억짜리 회사를 혼자 돌리는 비결은 AI가 아니라 '토큰 수'입니다. 코드가 20만 토큰 이하면 AI가 다 읽고 다 씁니다."
