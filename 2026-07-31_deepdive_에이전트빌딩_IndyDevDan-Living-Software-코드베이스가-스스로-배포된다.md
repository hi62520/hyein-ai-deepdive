---
date: 2026-07-31
category: 에이전트빌딩
subject: IndyDevDan — Living Software, 코드베이스가 스스로 배포된다
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱에서 반복 실행하는 업무 하나를 골라 'In Loop → Out Loop' 체크리스트(입력/출력/자기수정조건 3줄)를 옵시디언에 작성한다
---

# IndyDevDan — Living Software, 코드베이스가 스스로 배포된다

## 누구/무엇인가

IndyDevDan(GitHub 핸들: disler)은 15년 이상의 프로덕션 엔지니어링 경력을 가진 소프트웨어 엔지니어이자, AI 에이전트 교육 플랫폼 agenticengineer.com의 창립자입니다. YouTube에서 2M+ 누적 조회수를 기록하며 50,000명 이상의 엔지니어를 가르쳐 왔고, "에이전틱 엔지니어"라는 개념 자체가 유행하기 전부터 이 분야를 개척했습니다. 그의 핵심 미션은 한 문장으로 요약됩니다: **"소프트웨어가 스스로 작동하도록 만드는 것(Build LIVING software)."** 대표 강의 *Tactical Agentic Coding(TAC)*은 2025년 업데이트 기준 14개 모듈, 6.5시간 분량이며 100개 이상의 실전 자산(코드·프롬프트·아키텍처 다이어그램)을 포함합니다. Claude Code·Cursor·Aider 등 실제 도구를 프로덕션 환경에서 다뤄 본 경험을 그대로 커리큘럼에 녹였다는 점이 이론 중심 강의들과 차별화됩니다.

## 무엇이 특별한가

### 1. "In Loop → Out Loop → ZTE" 3단계 자율화 프레임워크

IndyDevDan이 제시하는 에이전트 성숙도 모델은 단계적 자율화입니다. **In Loop**는 인간이 매 단계 개입하는 전통적 방식, **Out Loop**는 에이전트가 실행하고 인간은 결과만 검토하는 단계, **ZTE(Zero Touch Execution)**는 에이전트가 계획·실행·자기수정까지 독립적으로 완료하는 단계입니다. 핵심은 "다음 단계로 이동하려면 무엇을 에이전트에게 가르쳐야 하는가"를 명확히 정의하는 것입니다. 대부분의 솔로 개발자는 In Loop에 머물며 에이전트를 단순 코드 자동완성 도구로 씁니다. IndyDevDan은 Out Loop 진입만으로도 개인 생산성이 3-5배 뛴다고 주장합니다.

### 2. 12 Leverage Points — 에이전트 자율성을 체계적으로 높이는 체크리스트

IndyDevDan의 강의에서 가장 자주 언급되는 개념이 **12 Leverage Points**입니다. 구체적 목록은 강의 자료 전체에 산포되어 있지만, 핵심 사상은 "에이전트 자율성을 임의로 높이지 말고, 레버리지 포인트를 순서대로 강화하라"는 것입니다. 대표적 레버리지 포인트로는 표준 출력 형식 정의, 타입 시스템 활용, 자동화 테스트 통합, 아키텍처 가이드 내장이 꼽힙니다. "제약을 추가할수록 에이전트는 더 자유로워진다(The more constraints you add, the freer the agent becomes)"는 역설이 이 프레임워크의 정수입니다.

### 3. AFK Agents — 잠자는 동안 코드가 완성된다

**AFK(Away From Keyboard) Agent**는 IndyDevDan이 자주 사용하는 표현으로, 개발자가 자리를 비운 사이에도 계획을 세우고, 실행하고, 실패 시 자기수정까지 완료하는 에이전트를 말합니다. 2025년 11월 유튜브 영상 *"The One Agent to RULE them ALL"*에서 그는 이렇게 말했습니다: **"엔지니어의 제약은 더 이상 '무엇을 할 수 있는가'가 아니라 '에이전트에게 무엇을 가르칠 수 있는가'다."** 이 한 문장이 AFK Agent 철학의 전부입니다. 비서앱·ERP 같은 반복적 업무 자동화에 직접 적용 가능한 개념입니다.

### 4. Single-File Agents — 복잡성보다 집중력

GitHub 저장소 *single-file-agents*에서 IndyDevDan은 하나의 Python 파일에 단일 목적 에이전트를 압축하는 패턴을 실험합니다. JQ 명령 생성기, DuckDB SQL 에이전트, CSV 변환 에이전트, 웹 스크래퍼 등을 각각 독립 파일로 구현합니다. 철학은 단순합니다: **"훌륭한 패턴 하나를 만들면 무한 반복할 수 있다."** 복잡한 멀티에이전트 프레임워크보다 먼저 단일 에이전트를 완전히 이해하는 것이 실전 생산성에 더 빠른 지름길이라는 주장입니다.

### 5. The Library — 스킬·에이전트·프롬프트의 사설 배포 시스템

2025년 후반 IndyDevDan이 공개한 *the-library* 프로젝트는 개인 또는 팀이 만든 에이전트 역량(Skills, Subagents, Prompts)을 library.yaml 카탈로그 하나로 관리하고, 필요할 때 온디맨드로 가져다 쓰는 시스템입니다. 특징은 별도의 CLI나 빌드 툴 없이 **마크다운 에이전트 명령어** `/library add`, `/library use`만으로 작동한다는 점입니다. "스킬 폭증(skill sprawl)" — 수백 개의 AI 역량이 여러 레포에 흩어져 버전이 제각각인 상태 — 을 해결하기 위한 실용적 대응책입니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**  
비서앱에서 매일 반복하는 업무 하나(예: 주문 집계, 공구 정산 요약)를 꺼내서 'In Loop → Out Loop' 체크리스트를 옵시디언에 작성합니다. 입력 데이터 형식 / 기대 출력 형식 / 자기수정 조건 세 줄이면 충분합니다. 이것이 ZTE로 가는 첫 번째 Leverage Point입니다.

**이번 주 1-2시간 (mid)**  
IndyDevDan의 Single-File Agent 패턴을 참고하여 와당탕 주문 데이터를 받아 공구별 집계표를 CSV로 출력하는 파이썬 단일 파일 에이전트를 만들어 봅니다. 아래 뼈대를 시작점으로 사용하세요:

```python
# wadangtang_order_agent.py
import anthropic, csv, json
from pathlib import Path

SYSTEM = """
당신은 와당탕연구소 공동구매 집계 에이전트입니다.
입력: 주문 JSON / 출력: 상품별 수량·금액 CSV
자기수정 조건: 출력 칼럼 누락 시 재시도 1회
"""

def run(order_data: dict) -> str:
    client = anthropic.Anthropic()
    response = client.messages.create(
        model="claude-sonnet-5",
        max_tokens=2048,
        system=SYSTEM,
        messages=[{"role": "user", "content": json.dumps(order_data, ensure_ascii=False)}]
    )
    return response.content[0].text
```

**이번 달 실험 (macro)**  
The Library 패턴을 와당탕 비서앱에 이식합니다. `library.yaml`에 현재 보유한 Claude Code Skills(주문집계·재고알림·캡션생성 등)의 경로를 등록하고, 신규 프로젝트 시작 시 `/library use 주문집계` 한 줄로 즉시 불러올 수 있는 체계를 구축합니다. 측정 지표: 새 자동화 업무 셋업 시간이 현재 대비 50% 단축되는지 확인합니다.

## 한국 솔로 운영자 맥락에서 주의

**ZTE는 도착지가 아니라 방향입니다.** IndyDevDan의 강의 대상은 "중급 이상 엔지니어"로 명시되어 있습니다. TAC 코스 자체가 Git·Node.js·Python·테스트 경험을 전제하며 입문자에게는 권장하지 않습니다. 와당탕의 상황처럼 풀스택 개발을 혼자 하면서 동시에 운영도 병행하는 경우, ZTE를 목표로 모든 업무를 한 번에 자동화하려다 컨텍스트가 분산될 수 있습니다. **In Loop 업무를 완전히 장악한 뒤, Out Loop로 하나씩 이전**하는 것이 현실적 전략입니다.

**"생산성 도구"로 접근하면 레버리지를 놓칩니다.** IndyDevDan의 핵심 주장은 에이전트를 코파일럿(보조 도구)이 아니라 **팀원**으로 설계하라는 것입니다. 비서앱에 "Claude한테 물어봐"를 붙이는 수준과, "Claude가 주문 집계→알림→정산 초안까지 독립 실행"하는 수준은 레버리지 규모가 완전히 다릅니다. 지금 내가 In Loop 단계에 머물고 있는지 Out Loop를 향해 설계하고 있는지를 주기적으로 점검하세요.

## 더 깊이 보려면

- [IndyDevDan YouTube 채널](https://www.youtube.com/@indydevdan)
- [Tactical Agentic Coding 코스](https://agenticengineer.com/tactical-agentic-coding)
- [The Library (GitHub)](https://github.com/disler/the-library)
- [Single-File Agents (GitHub)](https://github.com/disler/single-file-agents)
- [VSCode Snippets: Skills·Subagents·Agentic Prompts](https://gist.github.com/disler/d9f1285892b9faf573a0699aad70658f)
- [The One Agent to RULE them ALL (YouTube)](https://www.youtube.com/watch?v=p0mrXfwAbCg)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: 에이전트를 도입했는데도 여전히 내가 더 바쁘다. 왜냐하면 에이전트가 내 지시를 기다리고 있기 때문이다. 지시를 없애지 않으면 자동화가 아니라 더 정교한 수동 작업이다.
- **숫자**: 50,000명 이상의 엔지니어 교육, 2M+ YouTube 조회수, 14개 모듈 6.5시간 — 이 숫자보다 중요한 건 그가 "에이전틱 엔지니어"라는 단어가 없던 시절부터 이 개념을 가르쳤다는 사실.
- **삽질**: 대부분의 개발자는 Claude Code를 쓰면서도 여전히 In Loop에 머문다. 매 단계 프롬프트를 입력하고, 결과를 확인하고, 다음 단계를 지시한다. AFK Agent를 만드는 것과 AI 보조 코딩을 하는 것은 근본적으로 다른 작업이다.
- **훅**: "당신이 자는 동안 코드가 완성되어 있으려면, 지금 당장 에이전트에게 '자기수정 조건'을 가르쳐야 합니다. 대부분의 개발자는 이 조건을 정의하는 법을 배운 적이 없습니다."
