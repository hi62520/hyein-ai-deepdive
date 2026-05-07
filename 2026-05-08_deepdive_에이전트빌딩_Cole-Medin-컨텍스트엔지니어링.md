---
date: 2026-05-08
category: 에이전트빌딩
subject: Cole Medin — 바이브코딩을 버리고 컨텍스트 엔지니어링으로
tags: [AI탐구, deepdive]
starred: false
micro_action: CLAUDE.md에 "AI 레이어" 섹션 추가 — 비서앱/ERP 코드베이스 규칙·예제·검증 체크리스트 3줄씩 적어두기
---

# Cole Medin — 바이브코딩을 버리고 컨텍스트 엔지니어링으로

## 누구/무엇인가

Cole Medin은 Dynamous AI 창업자이자 oTTomator.ai CTO로, AI 에이전트 개발 분야에서 가장 빠르게 성장하는 교육 크리에이터 중 한 명입니다. 유튜브 채널 구독자 185,000명(2026년 1월 기준)을 보유하며 매주 일요일·수요일 에이전트 빌딩 튜토리얼을 꾸준히 업로드합니다. 그의 오픈소스 프로젝트 Archon은 GitHub에서 13,600개 이상의 스타를 받으며 "AI 코딩 어시스턴트를 위한 커맨드 센터"로 자리잡았습니다. 단순히 도구를 소개하는 데 그치지 않고, AI 코딩이 왜 실패하는지에 대한 근본 원인을 체계적으로 분석해 자신만의 방법론인 **컨텍스트 엔지니어링(Context Engineering)**을 제시한다는 점이 독보적입니다. 2026년 AI Coding Summit과 GitNation Amsterdam 등 굵직한 컨퍼런스에 연사로 초청받으며 업계 공인 전문가로 올라섰습니다.

---

## 무엇이 특별한가

### 1. "바이브코딩은 사기다" — 근본 문제 정의

Cole은 Andrej Karpathy가 대중화한 "바이브코딩(vibe coding)"을 정면으로 비판합니다. 그가 진단한 핵심은 이렇습니다: **"AI 코딩 어시스턴트가 실패하는 이유는 모델이 나빠서가 아니라, 개발자가 제공하는 컨텍스트가 엉망이기 때문이다."** 좋은 프롬프트 한 줄로 코드를 뽑아내는 바이브코딩은 소규모 프로토타입에선 통할 수 있지만, 실제 프로덕션 레벨 프로젝트에서는 반드시 무너진다는 것. 그의 대안인 컨텍스트 엔지니어링은 *"프롬프트 엔지니어링보다 10배, 바이브코딩보다 100배 낫다"*는 주장을 직접 GitHub README에 박아뒀습니다.

### 2. PRP 프레임워크 — AI에게 건네는 설계도

Cole의 컨텍스트 엔지니어링의 핵심 도구는 **PRP(Product Requirements Prompt)**입니다. 기존 PRD(기획 문서)에서 착안했지만, AI 코딩 어시스턴트에게 최적화된 형태로 재설계됐습니다. PRP는 단순한 기능 설명을 넘어 아키텍처 결정, 코드 예시 패턴, 검증 기준, 베스트 프랙티스까지 명세합니다. 실제 워크플로우는 두 개의 Claude Code 커맨드로 단순화됩니다:

- **`/generate-prp INITIAL.md`**: 코드베이스를 스캔하고 문서를 수집해 종합 PRP 청사진을 자동 생성
- **`/execute-prp PRPs/feature-name.md`**: PRP 컨텍스트를 읽고, 계획 수립 → 구현 → 자체 검증의 3단계를 순서대로 실행

이 방식을 쓰면 AI가 코드베이스의 기존 패턴을 이해하고 일관된 스타일로 구현하며, 검증 단계에서 스스로 오류를 발견하고 수정하는 루프가 완성됩니다.

### 3. PIV 루프 + 5개 황금 규칙 — 에이전트 엔지니어링 방법론

Cole이 2026년 AI Coding Summit 2시간 워크숍에서 공개한 방법론의 핵심은 **PIV 루프(Plan → Implement → Validate)**입니다. 여기에 "5개 황금 규칙"을 결합합니다:

1. **Commandify everything** — 반복 워크플로우는 모두 재사용 커맨드로 변환
2. **Reduce assumptions** — 단계마다 가정 대신 명확한 질문
3. **Context is king** — 계획과 구현 단계를 분리, 글로벌 규칙 비대화 방지
4. **Git log as memory** — 잦고 구체적인 커밋이 에이전트의 기억 자료가 된다
5. **System evolution** — 에이전트의 실수가 AI 레이어를 개선하는 피드백 루프

특히 **"AI 레이어(AI Layer)"** 개념이 실용적입니다. 모든 코드베이스에 코드 레이어와 AI 레이어(`.claude/` 폴더 안의 규칙·문서·커맨드·스킬)가 병렬로 존재한다고 봅니다. AI 레이어의 개선 사항도 코드 변경처럼 버전 관리하고 리뷰해야 한다는 것이죠.

### 4. Archon — AI가 AI를 짓는 오픈소스 하네스

Archon은 "AI 코딩을 결정론적이고 반복 가능하게 만드는 최초의 오픈소스 하네스 빌더"입니다. 개발 프로세스(계획, 구현, 검증, 코드 리뷰, PR 생성)를 YAML 워크플로우로 정의해 모든 프로젝트에 일관 적용합니다. 2025년 7월 Archon V2 알파가 Dynamous 커뮤니티에 비공개 출시됐고, 이후 공개 베타로 전환됐습니다. Archon의 정의 자체가 흥미롭습니다: *"Dockerfile이 인프라에, GitHub Actions가 CI/CD에 한 것을 AI 코딩 워크플로우에 적용한다."*

### 5. 로컬 AI 스택 — 프라이버시+비용 최적화 올인원 패키지

Cole은 `local-ai-packaged` 레포를 통해 Ollama + Supabase + n8n + Open WebUI + Flowise + Neo4j + Langfuse + SearXNG를 Docker Compose 하나로 로컬에서 돌리는 패키지를 공개했습니다. "클라우드 API 비용 없이, 데이터를 로컬에 두면서, 에이전트를 실전 수준으로 돌리는" 개발 환경입니다. 이 스택이 그의 AI 에이전트 마스터클래스 튜토리얼의 실습 환경으로 사용됩니다.

---

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱 또는 ERP 레포의 루트에 `CLAUDE.md` 파일을 열고 "AI 레이어" 섹션을 추가합니다. 코드베이스 규칙 3줄, 자주 쓰는 패턴 예시 3줄, 커밋 전 자체 검증 체크리스트 3줄. Cole의 5 황금 규칙 중 "Context is king"을 직접 실천하는 30분입니다. `micro_action`과 동일.

**이번 주 1-2시간 (mid)**: PRP 워크플로우를 비서앱 신기능 1개에 적용해 봅니다. `INITIAL.md`에 추가할 기능 요구사항을 작성하고, Claude Code의 `/generate-prp` 커맨드(또는 직접 프롬프트로 유사 흐름 구현) → 구현 → 자체 검증의 3단계를 한 사이클 돌립니다. 코드 스니펫 예시:

```bash
# .claude/commands/ 폴더에 generate-prp.md 파일 생성
mkdir -p .claude/commands
cat > .claude/commands/generate-prp.md << 'EOF'
# Generate PRP
Read INITIAL.md, analyze the codebase structure in src/, review existing patterns in examples/, 
then generate a comprehensive PRP (Product Requirements Prompt) saved to PRPs/$ARGUMENTS.md.
Include: architecture decisions, code examples matching existing patterns, validation checklist.
EOF
```

**이번 달 실험 (macro)**: ERP 개발 워크플로우 전체를 PIV 루프로 전환합니다. 모든 새 기능마다 PRP를 먼저 생성하고, AI 레이어(`.claude/` 폴더)를 기능 단위로 커밋해 버전 관리합니다. 측정 지표: 첫 구현 후 수동 수정 횟수, 기능당 개발 사이클 시간, AI 오류 재발률(같은 실수가 AI 레이어 업데이트 후 줄었는지).

---

## 한국 솔로 운영자 맥락에서 주의

**그대로 따라하면 설정에 파묻힌다.** Cole의 방법론은 정교하지만 초기 세팅 비용이 있습니다. `.claude/` 폴더 구조, CLAUDE.md 작성, PRP 템플릿 커스터마이징까지 처음 완성하는 데 반나절 이상 걸릴 수 있습니다. 와당탕+느린호밀처럼 운영과 개발을 동시에 돌리는 솔로라면, 전체 시스템을 한 번에 도입하기보다 PRP 하나, 커맨드 하나씩 점진적으로 추가하는 것이 현실적입니다.

**185,000명 구독자 기반이 전제된 교육 사업 모델.** Dynamous AI Mastery 커뮤니티·강의는 Cole의 대규모 유튜브 오디언스가 있어서 작동하는 모델입니다. 방법론의 기술 핵심은 충분히 가져올 수 있지만, 그의 콘텐츠 사업 구조를 직접 벤치마킹하려면 선행 오디언스 빌딩이 필요하다는 점을 감안해야 합니다.

---

## 더 깊이 보려면

- [Cole Medin GitHub — context-engineering-intro](https://github.com/coleam00/context-engineering-intro)
- [Cole Medin GitHub — ai-transformation-workshop](https://github.com/coleam00/ai-transformation-workshop)
- [Cole Medin GitHub — Archon](https://github.com/coleam00/Archon)
- [Cole Medin GitHub — local-ai-packaged](https://github.com/coleam00/local-ai-packaged)
- [Cole Medin YouTube Channel](https://www.youtube.com/@ColeMedin)
- [Dynamous AI Mastery 커뮤니티](https://dynamous.ai/)

---

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "AI 코딩 어시스턴트에게 시켰는데 왜 이상한 코드만 나올까요?" — 모델 탓이 아니라 컨텍스트 탓입니다. 대표님이 AI에게 건네는 정보가 부실하면, AI는 최선의 추측으로 빈 자리를 채웁니다.
- **숫자**: Archon GitHub 스타 13,600+개 / 유튜브 구독자 185,000명 / 컨텍스트 엔지니어링은 바이브코딩보다 100배 효과적 (Cole 본인 주장, context-engineering-intro README 명시).
- **삽질**: Cole 본인이 고백한 초기 실수 — "AI에게 CLAUDE.md 없이 코딩 시키면 프로젝트 규칙을 전혀 모른 채 짭니다. 저도 그렇게 6개월을 날렸습니다."
- **훅**: *"당신의 AI 코딩 어시스턴트가 틀린 코드를 내놓는 이유는 AI가 멍청해서가 아닙니다. 당신이 AI에게 충분히 설명하지 않았기 때문입니다."*
