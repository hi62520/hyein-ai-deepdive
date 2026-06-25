---
date: 2026-06-26
category: 에이전트빌딩
subject: AI Jason — 역공학으로 8M 뷰, 주말 실험이 6.6k 스타 오픈소스가 된 에이전트 빌더
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱 Claude Code 태스크 1개를 git worktree + sub-agent 패턴으로 분리해 병렬 실행해보기 (30분)
---

# AI Jason — 역공학(Reverse Engineering)이 에이전트 빌더의 가장 강력한 콘텐츠다

## 누구/무엇인가

AI Jason의 본명은 Jason Zhou, 시드니 기반 프로덕트 디자이너입니다. YouTube 채널 @AIJasonZ에서 8M+ 뷰를 기록 중이며, 주력 콘텐츠는 Claude Code·Cursor·Manus 같은 AI 도구를 "뜯어보는" 역공학 튜토리얼입니다. Relevance AI(멀티에이전트 플랫폼)에서 Head of Product을 역임한 뒤 독립해, AI Builder Club($37/월, 1,000명+ 빌더)과 오픈소스 프로젝트 SuperDesignDev를 동시에 운영 중입니다. 그는 "3년 이상 AI 제품을 직접 만들어온 VC 지원 창업자"라고 자신을 소개하며, 이론보다 구현에 무게를 두는 스타일로 기술 커뮤니티에서 신뢰를 쌓았습니다. SuperDesignDev는 2025년 6월 주말 실험으로 시작해 6.6k GitHub 스타를 획득했고, Anthropic의 Claude Code SDK를 실제 제품에 최초로 적용한 케이스 중 하나로 언급됩니다.

## 무엇이 특별한가

### 1. "역공학" 하나로 8M 뷰 — 콘텐츠 해자

Jason의 채널을 관통하는 한 단어는 **역공학(reverse engineering)**입니다. "Claude Code가 실제로 어떻게 작동하는가", "Cursor의 컨텍스트 창 관리는 내부적으로 어떤 패턴인가" 같은 블랙박스를 해체해 보여주는 영상들이 구독자를 모았습니다. 일반적인 AI 채널이 "이 도구 써보세요"를 외칠 때, Jason은 "이 도구가 이 패턴을 쓰는 이유는 이렇습니다"로 한 단계 깊이 들어갑니다. 대부분의 튜토리얼 채널이 표면적 사용법을 다루는 레드오션에서, 내부 메커니즘 설명이라는 블루오션을 선점한 셈입니다.

### 2. 병렬 에이전트 발견 → 즉시 제품화 — SuperDesignDev 탄생

2025년 6월, Jason은 Claude Code의 숨겨진 패턴을 발견합니다. **"Claude Code가 sub-agent에게 병렬 태스크를 할당할 수 있고, git worktree와 결합하면 각 태스크가 독립된 샌드박스 환경에서 동시에 실행된다"**는 것. 그의 트윗 원문: *"Claude Code can assign parallel tasks to sub agents. Integrate with git worktree to create sandbox env. This means you can get Claude Code generate 10 designs at the same time."* 이 인사이트를 즉시 제품으로 구현한 것이 SuperDesignDev입니다. Cursor·Windsurf·VS Code·Claude Code 안에 직접 설치되는 익스텐션으로, 자연어 한 줄에 UI 디자인 10개가 동시에 생성됩니다. "주말 실험으로 시작해서 validate할 생각이었다"고 그는 밝혔으며, 결과는 6.6k 스타·718 포크로 화답했습니다.

### 3. 학습 속도를 콘텐츠 속도로 전환하는 구조

Jason의 루프는 단순합니다: **직접 빌드 → 역공학 → 영상·글 → AI Builder Club 강의 자료화**. Relevance AI에서 Head of Product으로 멀티에이전트 플랫폼의 내부를 3년 가까이 다뤄본 경험이, "무엇을 가르쳐야 시장에 필요한가"를 정확하게 고르는 필터가 됩니다. SuperDesignDev를 만든 직후 AI Builder Club에 관련 학습 내용이 추가되고, 이 내용이 다시 YouTube 영상으로 리패키징됩니다. 강의 재료와 유튜브 소재와 오픈소스 신뢰가 동시에 생산되는 삼각 플라이휠입니다.

### 4. $37/월 × 1,000명+ = 오픈소스를 지속 가능하게 만드는 구조

AI Builder Club은 월 37달러, 멤버 1,000명+ 기준 월 3.7만 달러(약 5,000만원) 이상의 안정적인 현금흐름입니다. 이 수익이 SuperDesignDev 같은 오픈소스 프로젝트를 "무료로 만들어도 되는" 기반이 됩니다. 오픈소스로 6.6k 스타를 쌓으면 그 신뢰가 다시 멤버십 전환율을 높이는 순환 구조. Jason은 Skool에서 출발해 자체 도메인 aibuilderclub.com으로 이전하며 커뮤니티 소유권도 확보했습니다. 플랫폼 의존도를 낮추는 전략입니다.

### 5. 오픈소스 제품 + Chrome Extension + Marketplace 삼중 배포

SuperDesignDev는 단일 제품이지만 배포 채널이 세 갈래입니다: ① GitHub 오픈소스(6.6k 스타), ② VS Code/Cursor Marketplace 익스텐션, ③ 웹사이트 클로닝용 Chrome Extension. 같은 핵심 기술로 도달 범위를 최대화하는 전략입니다. 한 번 만들어서 세 플랫폼 디스커버리에 동시 노출됩니다.

---

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro):**  
Claude Code로 비서앱 기능 한 가지를 작업할 때, `git worktree add` 명령으로 별도 브랜치를 두 개 만들고 sub-agent에게 각각 다른 UI 접근 방식을 병렬로 지시해보세요. `"Try approach A in worktree-a, approach B in worktree-b simultaneously"` 패턴 한 번 경험하는 게 목표입니다. SuperDesignDev 방식 그대로입니다.

**이번 주 1-2시간 (mid):**  
비서앱 또는 ERP의 반복 리포트(일일 매출 요약, 주문 현황 등) 생성 태스크를 Jason의 "에이전트 워크포스" 패턴으로 분해해보세요. 예: ① 데이터 수집 에이전트, ② 요약 작성 에이전트, ③ 슬랙/텔레그램 발송 에이전트로 역할 분리. 세 에이전트가 pipeline으로 연결되는 구조를 n8n 또는 Claude Code workflow로 간단히 구현해봅니다.

```python
# Claude Code workflow 예시: 비서앱 일일 리포트 에이전트
# Task 1 (sub-agent A): 오늘 주문 데이터 수집 → JSON
# Task 2 (sub-agent B): JSON → 한국어 요약문 생성
# Task 3 (main): 텔레그램 발송
# → git worktree로 A, B를 병렬로 돌리고 main이 결과를 통합
```

**이번 달 실험 (macro):**  
느린호밀 강의 기획에서 Jason의 역공학 콘텐츠 공식을 적용해봅니다. "Claude Code가 실제로 어떻게 작동하는가"처럼, 대표님의 비서앱/ERP 개발 과정에서 발견한 인사이트를 "내부 메커니즘 해체" 포맷으로 유튜브 1편 또는 뉴스레터 1편으로 만들어보세요. 측정 지표: 영상 조회수 vs 기존 영상 대비, 뉴스레터 오픈율 vs 평균 대비.

---

## 한국 솔로 운영자 맥락에서 주의

**병렬 에이전트는 컨텍스트 관리 비용도 병렬로 증가합니다.** SuperDesignDev처럼 UI 디자인(비교적 독립적인 태스크)에는 병렬 패턴이 매우 효과적이지만, 비서앱·ERP처럼 데이터 일관성이 중요한 영역에서는 동시 쓰기 충돌을 주의해야 합니다. Jason의 git worktree 격리 패턴을 그대로 쓰더라도, 최종 병합 단계에서 충돌 해소 로직을 반드시 설계해두세요.

**"주말 실험"은 배경이 뒷받침될 때만 6.6k 스타가 됩니다.** Jason은 Relevance AI Head of Product 경력과 1,000명+ 커뮤니티, 그리고 8M 뷰 유튜브 채널이라는 신뢰 인프라가 있었기 때문에 SuperDesignDev가 빠르게 확산됐습니다. 신뢰 자산 없이 오픈소스를 던지면 스타는 안 쌓입니다. 와당탕/느린호밀 기반의 공개 빌딩 기록이 먼저입니다.

---

## 더 깊이 보려면

- [SuperDesignDev GitHub (6.6k stars)](https://github.com/superdesigndev/superdesign)
- [AI Builder Club 공식 사이트](https://www.aibuilderclub.com/)
- [Jason Zhou Twitter @jasonzhou1993](https://twitter.com/jasonzhou1993)
- [YouTube @AIJasonZ](https://www.youtube.com/@AIJasonZ)
- [Claude Code 병렬 sub-agent 트윗 원문](https://x.com/jasonzhou1993/status/1938195729824330201)

---

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: AI 튜토리얼은 넘쳐나는데 "왜 이렇게 작동하는가"를 설명하는 건 없다. 도구를 쓰면서 내부 패턴을 모르면, 도구가 실패할 때 왜 실패하는지 모른다.
- **숫자**: 주말 실험 하나가 6.6k GitHub 스타. SuperDesignDev TypeScript 익스텐션, Claude Code SDK 기반, 718 포크. AI Builder Club $37/월 × 1,000명+ = 월 3,700만원+ 현금흐름 추정.
- **삽질**: Jason은 MetaGPT·ChatDev 같은 초기 멀티에이전트 프레임워크도 직접 뜯어봤습니다. "컨텍스트가 너무 길어지면 에이전트가 자기가 무슨 역할인지 잊어버린다"는 실패 경험이 SuperDesignDev의 역할 격리(worktree) 설계로 이어졌습니다.
- **훅**: "Claude Code로 디자인 10개를 동시에 뽑는다고?" — 그게 실제로 됩니다. 그리고 이 패턴을 주말에 발견해서 오픈소스로 만들었더니 6,600명이 스타를 눌렀습니다.
