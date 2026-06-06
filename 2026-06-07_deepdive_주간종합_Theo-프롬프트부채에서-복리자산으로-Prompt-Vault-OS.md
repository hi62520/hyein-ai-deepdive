---
date: 2026-06-07
category: 주간종합
subject: Theo t3gg 재조명 — "프롬프트 부채"에서 "프롬프트 복리 자산"으로 Prompt Vault OS 설계
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱 가장 자주 쓰는 프롬프트 1개를 skills/ 폴더에 SKILL.md로 저장하고 frontmatter에 model_version·last_tested·score 3필드 추가
---

# Theo t3gg 재조명 — "프롬프트 부채"에서 "프롬프트 복리 자산"으로

## 누구/무엇인가

6월 5일 목요일, T3 스택 창시자이자 Ping Labs CEO Theo Browne의 핵심 주장 — **"프롬프트도 기술부채다"** — 를 다뤘습니다. 오늘 일요일 재조명은 그 진단의 다음 질문으로 넘어갑니다: **"그럼 어떻게 하면 프롬프트가 부채가 아니라 자산이 되는가?"**

Theo의 진단은 맞습니다. 모델이 41일마다 업데이트되는 세계에서, 아무렇게나 쌓인 프롬프트는 소리 없이 썩어갑니다. 그런데 코드도 관리하지 않으면 기술부채입니다. 코드를 자산으로 만드는 것은 버전 관리, 테스트, 모듈화입니다. 프롬프트에도 같은 원칙이 적용됩니다. 이번 주 다룬 인물들을 교차 연결하면 시스템이 보입니다: Anthropic의 Agent Skills(6/2), Marc Lou의 포트폴리오 복리(6/1), Theo의 부채 경고(6/5). 세 인사이트가 합쳐지면 **"솔로 운영자의 Prompt Vault OS"** 설계도가 나옵니다.

## 무엇이 특별한가

### 1. 자산 프롬프트의 3가지 조건 — 구체성·테스트가능성·모듈성

Theo가 "부채"로 진단하는 프롬프트는 공통점이 있습니다: 하나의 긴 덩어리이고, 출력 검증 방법이 없으며, 다른 프롬프트와 독립적으로 재사용되지 않습니다. "부채 프롬프트"의 반대편에 있는 "자산 프롬프트"는 세 조건을 만족합니다.

**첫째, 구체성(Specificity)**: 자산 프롬프트는 하나의 목적만 수행합니다. "와당탕연구소 주문 접수 메시지를 받아 아이템명·수량·배송주소를 JSON으로 파싱하라"는 자산이고, "고객 메시지를 처리하라"는 부채입니다. Anthropic이 Agent Skills 스펙에서 `SKILL.md`를 "500라인, 5,000토큰 이하"로 제한하는 이유가 이것입니다. 너무 많은 것을 하려는 프롬프트는 작아도 부채입니다.

**둘째, 테스트가능성(Testability)**: 자산 프롬프트는 "이 입력에 이 출력이 나와야 한다"는 기대치가 명확합니다. 2026년 기준으로 프롬프트 10개 이상을 프로덕션에서 운영하는 팀들이 "버전 관리"를 운영 3대 과제 1위로 꼽습니다. 테스트 없는 프롬프트는 소프트웨어로 치면 테스트 없는 함수와 같습니다. 모델 업데이트 후 조용히 회귀합니다.

**셋째, 모듈성(Modularity)**: 자산 프롬프트는 다른 프롬프트, 다른 에이전트에서 재사용됩니다. 비서앱에서 "주문 파싱" 프롬프트를 한 번 잘 만들면, 같은 모듈이 ERP 입고 처리에도, 텔레그램 봇 응답에도 재사용됩니다. Marc Lou가 "한 번 만든 강의 영상이 수년간 판매된다"고 했던 것과 같은 구조입니다. 프롬프트 1개 작성 시간 = 1회 투자. 잘 만든 프롬프트 모듈 = N개 에이전트 × M번 재사용.

### 2. Anthropic Agent Skills — 이미 업계 표준이 된 프롬프트 자산화 형식

프롬프트 모듈화의 사실상 업계 표준은 **Anthropic이 2025년 12월 오픈소스로 공개한 Agent Skills 포맷**입니다. agentskills.io에서 공개 표준으로 관리되고, Claude Code·Cursor·GitHub Copilot·Codex CLI·Gemini CLI 포함 20개 이상 플랫폼이 채택했습니다. Atlassian, Stripe, Canva, Figma, Notion, Sentry가 파트너로 참여했습니다.

포맷을 이해하면 솔로 운영자도 직접 구현할 수 있습니다. Agent Skills는 **3단계 점진적 로딩** 구조입니다.

**Discovery (스킬당 ~100토큰)**: 에이전트는 시작 시점에 스킬 이름과 설명만 로딩합니다. 50개 스킬 라이브러리를 갖고 있어도 발견 단계에서는 5,000토큰만 씁니다. 컨텍스트 부담 없이 방대한 전문 지식을 "책장에 꽂아둔" 형태입니다.

**Activation (최대 5,000토큰)**: 현재 작업에 해당 스킬이 필요하다고 판단되면 `SKILL.md` 전체를 로딩합니다. 목적, 절차, 출력 형식, 금지 사항이 담깁니다.

**Reference Loading (필요 시)**: 더 구체적인 예시나 템플릿이 필요하면 `references/` 또는 `assets/` 폴더에서 추가 파일을 로딩합니다.

이 구조가 곧 "자산 프롬프트의 파일 시스템 표현"입니다. `skills/주문-파싱/SKILL.md` 하나가 그대로 자산입니다. 특이한 점은 Theo 자신도 비판했던 Anthropic의 이 표준을 T3 Code에 지원 레이어로 포함했다는 것입니다. 비판과 실용주의가 공존하는 Theo식 방식입니다.

### 3. Prompt Vault OS — 옵시디언 Second Brain 연동 설계

대표님이 운영하시는 옵시디언 Second Brain과 연결하면 Prompt Vault가 완성됩니다. 핵심은 **프롬프트를 코드 저장소에만 두지 않고, 지식 관리 시스템으로도 가져오는 것**입니다. 코드 저장소 버전은 에이전트가 쓰고, 옵시디언 버전은 대표님이 검색하고 평가합니다.

```
Obsidian Vault/
└── AI-OS/
    └── prompts/
        ├── _template.md          ← 모든 프롬프트의 공통 틀
        ├── 비서앱/
        │   ├── 주문-파싱.md
        │   ├── 재고-확인.md
        │   └── 응답-초안.md
        └── ERP/
            ├── 매출-집계.md
            └── 발주-결정.md
```

각 프롬프트 파일의 frontmatter는 다음과 같습니다:

```yaml
---
skill_name: 주문-파싱
model_version: claude-sonnet-4-6
last_tested: 2026-06-07
score: 4/5          # 구체성·테스트가능성·모듈성 평균
status: active      # active / stale / deprecated
notes: 수량 없는 메시지에서 간혹 null 반환 → 예시 1개 추가 필요
---
```

이렇게 관리하면 Anthropic이 새 모델을 출시할 때 `status: stale`로 표시된 프롬프트만 점검하면 됩니다. 30개를 전부 재작성할 필요가 없습니다.

### 4. 복리 계산 — 시스템이 없으면 시간이 지날수록 손해다

Theo의 공포 시나리오를 숫자로 뒤집어봅니다. Anthropic 모델 업데이트 주기: 약 41일. 연간 약 9회 업데이트. 프롬프트 30개를 관리하지 않으면 6개월 후 약 15개가 성능 저하 상태입니다. 점검 비용: 개당 약 15분 × 15개 = **225분(약 4시간)**.

Prompt Vault OS 유지 비용: 매 모델 업데이트 후 score 기반 우선순위 정렬 → 하위 20%(6개)만 집중 점검 → **총 90분**. 차이: 회당 135분 절감.

Marc Lou식으로 표현하면 이렇습니다. "한 번 시스템을 설계하면, 시스템이 나 대신 프롬프트를 관리한다." Theo가 경고한 부채 축적 속도보다 시스템 유지 속도가 빠르면, 시간이 지날수록 경쟁 우위가 벌어집니다. 이것이 프롬프트의 복리입니다.

### 5. "Stock 설정에 가깝게" + Vault = 모순이 아니라 조합이다

Theo의 최종 권고는 "설정을 최소화하고 써드파티 유지보수 도구에 맡겨라"입니다. 이것과 Prompt Vault는 모순이 아닙니다. 전략은 이렇습니다: CLAUDE.md 전역 설정은 최소화하고(Theo 권고 준수), 대신 Skills 폴더에서 필요할 때만 로딩하는 모듈형 구조를 씁니다(Agent Skills 표준 준수). 전역 컨텍스트는 가볍게 두고, 전문 지식은 정확한 순간에만 주입합니다. 에이전트에게 "모든 것이 미리 칠해진 캔버스"를 주는 것보다 "빈 캔버스 + 정리된 도구함"을 주는 것이 훨씬 낫습니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱 가장 자주 쓰는 프롬프트 1개를 `skills/` 폴더(코드베이스)와 옵시디언 `AI-OS/prompts/`(second brain)에 동시 저장합니다. `SKILL.md`에 목적·입력·출력 형식·금지사항을 적고, frontmatter에 `model_version: claude-sonnet-4-6`, `last_tested: 2026-06-07`, `score: ?/5`를 추가합니다. 점수는 지금 당장 채점하지 않아도 됩니다. **필드를 만드는 것 자체가 시작**입니다.

**이번 주 1-2시간 (mid)**: 비서앱 상위 5개 프롬프트를 3기준으로 스코어링합니다.

```python
# 프롬프트 자산 점수 계산 (간이 버전)
def score_prompt(skill_md_content: str, has_examples: bool) -> float:
    # 구체성: ## 섹션 수가 3개 이하면 단일 목적
    specificity = 5 if skill_md_content.count("##") <= 3 else 3
    # 테스트가능성: examples/ 폴더 존재 여부
    testability = 5 if has_examples else 2
    # 모듈성: depends_on 없이 독립 작동 가능
    modularity = 4 if "depends_on" not in skill_md_content else 2
    return round((specificity + testability + modularity) / 3, 1)

# 예시 실행
score = score_prompt(open("skills/주문-파싱/SKILL.md").read(), has_examples=True)
print(f"주문-파싱 점수: {score}/5")
```

**이번 달 실험 (macro)**: 다음 Anthropic 모델 업데이트 시 Prompt Vault의 score 변화를 추적합니다. score 3 이하인 프롬프트만 재작성하는 "선택적 유지보수" 파일럿. 측정 지표: 재작성 프롬프트 수, 에이전트 재시도율, 총 유지보수 시간. 목표: 이전 대비 유지보수 시간 30% 이상 단축.

## 한국 솔로 운영자 맥락에서 주의

**시스템 먼저, 프롬프트 나중 함정**: Prompt Vault 폴더 구조를 완벽하게 만들려다 정작 프롬프트를 한 개도 저장하지 못하는 경우가 있습니다. 폴더 구조보다 첫 번째 `SKILL.md` 하나가 더 중요합니다. 옵시디언 플러그인이나 자동화 스크립트는 5번째 프롬프트부터 고민해도 늦지 않습니다.

**채점 기준의 현지화**: 위의 3기준(구체성·테스트가능성·모듈성)은 일반적 기준입니다. 와당탕연구소 업무에는 "한국어 경어 처리 정확도"나 "느린호밀 주문 양식 특수성" 같은 도메인별 기준이 추가로 필요할 수 있습니다. 글로벌 프레임워크를 가져올 때는 "이것이 내 업종·내 고객·내 언어에도 맞는가"를 먼저 확인하십시오.

## 더 깊이 보려면

- [Anthropic Agent Skills 공식 문서](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview)
- [agentskills.io 표준](https://agentskills.io/home)
- [Langfuse — 오픈소스 프롬프트 CMS (셀프 호스팅 가능)](https://langfuse.com)
- [T3 Code GitHub](https://github.com/pingdotgg/t3code)
- [Promptarch 2026 베스트 프랙티스](https://promptarch.ai/blog/ai-system-prompt-best-practices-2026)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: CLAUDE.md를 3시간 정성껏 써놨는데, 모델 업데이트 하나에 전부 먹통이 됐습니다. 오류 메시지도 없이, 조용히.
- **숫자**: 프롬프트 10개 이상 프로덕션 운영 팀의 "프롬프트 버전 관리"가 운영 1위 과제. Anthropic 모델 업데이트 주기 41일, 연간 9회. 관리 없는 30개 프롬프트 → 6개월 후 15개 회귀.
- **삽질**: Theo 본인도 T3 Code에서 "전역 설정 최소화"를 실천하기까지 수개월의 커스터마이즈 삽질을 거쳤습니다. "설정은 stock에 가깝게"라는 결론은 이 삽질의 결과물입니다.
- **훅**: "코드는 버전 관리하면서 프롬프트는 왜 Notion 랜덤 페이지에 저장하십니까?"
