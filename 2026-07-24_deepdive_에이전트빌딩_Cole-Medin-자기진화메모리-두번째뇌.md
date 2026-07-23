---
date: 2026-07-24
category: 에이전트빌딩
subject: Cole Medin — Claude Code가 세션을 기억한다, 자기진화 메모리 설계
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱 레포 루트에 .claude/settings.json 열고 "hooks" 섹션 확인 — SessionEnd 훅이 없으면 오늘 추가 준비
---

# Cole Medin — Claude Code가 세션을 기억한다, 자기진화 메모리 설계

## 누구/무엇인가

Cole Medin은 Dynamous AI 창업자이자 oTTomator.ai CTO로, AI 에이전트 교육 분야에서 가장 빠르게 성장하는 오픈소스 빌더 중 한 명입니다. 유튜브 구독자 204,000명·누적 조회 1,080만 회를 보유하고, 오픈소스 하네스 빌더 Archon은 GitHub 스타 23,000개를 달성해 한때 전체 1위 트렌딩에 올랐습니다. 5월 deepdive에서 그의 컨텍스트 엔지니어링과 PRP 프레임워크를 다뤘는데, 그로부터 두 달도 안 된 2026년 4월 6일 그는 완전히 새로운 층위의 작업을 공개했습니다. 바로 **claude-memory-compiler** — Claude Code가 세션이 끝날 때마다 스스로 지식을 추출하고 구조화해서 영구 위키로 쌓는 자기진화 메모리 시스템입니다. GitHub에서 공개 48시간 만에 237개 스타를 받았고, 현재 1,300개 스타·314개 포크에 달합니다. 2026년 7월 21일 Personal AI Agents Summit에서는 *"Your Second Brain: Building Personal Agents That Actually Run Your Day with Claude Code"* 워크샵을 직접 진행했고, GOTO Copenhagen·GOTO Accelerate Chicago에서는 "The Validation-First Loop"를 주제로 발표하며 AI 시대의 병목이 코딩이 아닌 검증과 계획으로 이동했다고 주장합니다. Karpathy가 외부 문서를 컴파일하는 아이디어를 제시했다면, Cole은 그것을 **내부 대화 로그**로 뒤집었습니다.

## 무엇이 특별한가

### 1. Karpathy를 뒤집은 핵심 인사이트

Andrej Karpathy가 2026년 4월 발표한 LLM Knowledge Base 개념은 1.7백만 뷰를 기록한 충격적인 제안이었습니다. 핵심은 이렇습니다: "RAG처럼 매번 원본 문서를 검색하지 말고, LLM이 문서를 한 번 컴파일해서 구조화된 위키로 만들어두고 이후 쿼리는 그 위키에게 물어라." 컴파일러 비유 — 소스 코드를 매번 인터프리팅하지 않고 한 번 컴파일해서 바이너리로 만드는 것처럼.

Karpathy 원본은 **외부 데이터**(웹 문서, 논문)를 입력 소스로 삼습니다. Cole의 뒤집기는 **내부 데이터** — Claude Code 대화 세션 로그 — 를 입력으로 씁니다. 그 결과 "내가 두 달 전 ERP 결제 모듈에서 어떤 결정을 왜 내렸는지"를 Claude가 다음 세션에 즉시 알고 시작합니다. Karpathy의 말대로: *"Obsidian is the IDE, the LLM is the programmer, the wiki is the codebase, and you are the architect."* Cole은 이 구조를 코드베이스 그 자체에 내장시킨 것입니다.

### 2. 세 훅 라이프사이클 — 포착·추출·로드

시스템의 뼈대는 Claude Code의 `.claude/settings.json`에 정의되는 세 훅입니다:

- **SessionStart 훅**: 세션이 시작될 때 위키 인덱스를 컨텍스트로 주입. Claude가 대화를 시작하기 전에 "오늘 이 코드베이스에 대해 알아야 할 것"을 먼저 읽는다.
- **PreCompact 훅**: 컨텍스트 압축 직전에 현재 세션을 캡처. `/compact` 이후에도 메모리가 살아남는다.
- **SessionEnd 훅**: 세션 종료 시 대화 트랜스크립트를 저장하고, Claude Agent SDK를 백그라운드 프로세스로 스폰해서 핵심 결정·패턴·gotcha를 추출한다.

핵심은 **flush.py와 compile.py**의 두 스크립트입니다. flush.py는 세션 로그에서 "저장할 가치 있는 것"(결정 이유, 우회한 버그, 반복 패턴)만 추려 일별 로그에 추가합니다. compile.py는 오후 6시 이후 일별 로그가 변경됐을 때 자동 실행되어 구조화된 크로스레퍼런스 위키 아티클로 변환합니다. 별도 크론 잡 없이 자동 트리거됩니다.

### 3. RAG 없이도 된다는 역설

*"The large language model has been pretty good about auto-maintaining index files"* — Cole의 핵심 발견. 50~500개 아티클 규모의 개인 지식베이스에서는 벡터 DB·임베딩·시맨틱 서치가 필요 없습니다. 구조화된 마크다운 인덱스 파일과 백링크만으로 탐색이 충분합니다. 이것은 솔로 운영자에게 특히 중요합니다 — Pinecone·Weaviate 같은 벡터 인프라를 셋업하고 유지하는 비용 없이, 이미 쓰고 있는 Claude 구독(Max·Team·Enterprise) 내에서 1회 컴파일당 약 $0.20~0.30의 쿼터 소비만으로 작동합니다.

### 4. 복리 루프 — 쓸수록 똑똑해지는 에이전트

claude-memory-compiler의 가장 강력한 특성은 **복리 구조**입니다. 오늘 세션에서 결정한 아키텍처 선택이 오늘 밤 위키에 추가되고, 내일 세션 시작 시 Claude가 그것을 이미 알고 시작합니다. 한 달이 지나면 Claude는 대표님 코드베이스에 대해 "공동 창업자 수준의 암묵지"를 갖게 됩니다. git log가 무엇을 변경했는지를 기록한다면, 메모리 위키는 **왜** 그 결정을 내렸는지를 기록합니다. 두 가지는 완전히 다른 지식입니다.

### 5. AGENTS.md — 에이전트 자기인식 레이어

시스템의 또 다른 독특한 층위는 **AGENTS.md**입니다. 이 파일은 에이전트가 자기 인프라를 인식하게 만드는 메타레이어 — "나는 어떤 메모리 도구를 갖고 있고, 어떻게 검색하며, 어떻게 업데이트하는가"를 에이전트 스스로 알도록 설계됩니다. 결과적으로 Claude는 모르는 것을 만났을 때 먼저 자기 위키를 검색하고, 그래도 모르면 질문하는 행동 패턴을 습득합니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱 레포에서 `.claude/settings.json`을 열고 `hooks` 섹션을 확인합니다. SessionEnd 훅이 없다면 아래 최소 구조를 추가해두고, 다음 세션부터 Claude가 종료 시 핵심 결정을 직접 물어보도록 설정합니다. (오늘 micro는 "코드 설치"가 아니라 "내 레포에 적용할 준비가 됐는지 확인"입니다.)

```json
{
  "hooks": {
    "SessionEnd": [
      {
        "matcher": "",
        "hooks": [
          {
            "type": "command",
            "command": "python3 /path/to/claude-memory-compiler/flush.py"
          }
        ]
      }
    ]
  }
}
```

**이번 주 1-2시간 (mid)**: claude-memory-compiler를 비서앱 레포에 실제 설치합니다. 특히 ERP 모듈에서 "결제 처리 로직을 왜 이렇게 짰는가"를 AGENTS.md에 한 줄씩 수작업으로 씨앗 데이터로 입력합니다. Claude가 이후 세션에서 이 결정을 기억하고 일관성 있는 코드를 짜는지 비교 체크합니다.

```python
# flush.py가 추출하는 것의 예시 — 대화 트랜스크립트에서
key_decisions = [
    "결제 실패 시 retry 3회 후 ledger에 error 상태 기록 (반드시 DB 트랜잭션 롤백 선행)",
    "와당탕 주문서 파싱은 항상 KST 기준 날짜 처리 (UTC 변환 버그 2회 경험)",
]
# 이 결정들이 daily log → wiki 아티클로 진화
```

**이번 달 실험 (macro)**: 비서앱·ERP 두 레포에 각각 독립된 메모리 위키를 구성하고, 한 달 후 Claude에게 "ERP 결제 모듈의 주요 설계 결정을 요약해줘"를 물어봅니다. 측정 지표: 첫 번째 답변의 정확도 (실제 결정과 일치 여부), 같은 실수 반복 횟수, 컨텍스트 없이 시작한 세션 vs 위키 주입 세션의 초기 답변 품질 차이.

## 한국 솔로 운영자 맥락에서 주의

**"설치하면 알아서 된다"는 착각**. claude-memory-compiler는 초기 씨앗 데이터 없이는 빈 위키에서 출발합니다. 첫 2주는 세션마다 flush.py가 추출한 결과를 직접 검토해 "잘못 캡처된 것"과 "빠진 결정"을 수동 보정해야 합니다. 이 초기 교정 비용을 건너뛰면 낮은 품질의 위키가 자기진화해서 오히려 Claude를 혼란스럽게 만들 수 있습니다.

**모델 비용 착각 주의**. 현재 Claude Max/Team 구독 기반 동작이지만, 위키 아티클이 세션 시작마다 컨텍스트에 주입될 때 토큰 사용량이 누적됩니다. 위키가 수백 개 아티클로 커지면 SessionStart 주입 비용도 커집니다 — 인덱스 파일의 크기를 모니터링하고 핵심 아티클만 로드하도록 주기적으로 정리가 필요합니다.

## 더 깊이 보려면

- [coleam00/claude-memory-compiler GitHub](https://github.com/coleam00/claude-memory-compiler)
- [YouTube — I Built Self-Evolving Claude Code Memory w/ Karpathy's LLM Knowledge Bases](https://www.youtube.com/watch?v=7huCP6RkcY4)
- [Beyond RAG: How Andrej Karpathy's LLM Wiki Pattern Builds Knowledge](https://levelup.gitconnected.com/beyond-rag-how-andrej-karpathys-llm-wiki-pattern-builds-knowledge-that-actually-compounds-31a08528665e)
- [Personal AI Agents Summit 2026 — Cole Medin 워크샵 소개](https://opendatascience.com/personal-ai-agents-summit-2026/)
- [coleam00/mcp-mem0 — Mem0 기반 장기 메모리 MCP 서버](https://github.com/coleam00/mcp-mem0)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "Claude Code에게 같은 질문을 두 번 하는 것보다 허무한 게 없습니다. 어제 결정한 걸 오늘 또 설명해야 할 때마다 '이 에이전트는 기억이 없구나'를 체감합니다."
- **숫자**: GitHub 스타 1,300개·포크 314개 / 공개 48시간 내 237스타 / Karpathy 원글 1.7백만 뷰 48시간 / 1회 컴파일 비용 $0.20-0.30 구독 쿼터 / 추천 위키 규모 50-500 아티클.
- **삽질**: "RAG부터 깔아야 한다고 생각해서 Pinecone 셋업에 이틀을 썼는데, Cole의 시스템은 마크다운 인덱스만으로 개인 규모에서 충분히 작동합니다. 복잡한 인프라가 심플한 구조를 이긴다는 보장은 없습니다."
- **훅**: *"Claude Code가 어제 대화를 기억하지 못하는 게 당연하다고 생각하셨죠? Cole Medin은 그걸 당연하게 두지 않았습니다."*
