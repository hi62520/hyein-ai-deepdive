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

Cole Medin은 Dynamous AI 창업자이자 oTTomator.ai CTO로, AI 에이전트 개발 분야에서 가장 빠르게 성장하는 교육 크리에이터 중 한 명입니다. 유튜브 채널 구독자 185,000명(2026년 1월 기준)을 보유하며 매주 에이전트 빌딩 튜토리얼을 꾸준히 업로드합니다. 그의 오픈소스 프로젝트 Archon은 GitHub에서 13,600개 이상의 스타를 받으며 "AI 코딩 어시스턴트를 위한 커맨드 센터"로 자리잡았습니다.

## 무엇이 특별한가

### 1. "바이브코딩은 사기다" — 근본 문제 정의

Cole은 핵심을 이렇게 정의합니다: **"AI 코딩 어시스턴트가 실패하는 이유는 모델이 나빠서가 아니라, 개발자가 제공하는 컨텍스트가 엉망이기 때문이다."** 그의 대안인 컨텍스트 엔지니어링은 *"프롬프트 엔지니어링보다 10배, 바이브코딩보다 100배 낫다"*는 주장을 직접 GitHub README에 박아뒀습니다.

### 2. PRP 프레임워크 — AI에게 건네는 설계도

Cole의 핵심 도구는 **PRP(Product Requirements Prompt)**입니다. 기존 PRD에서 착안했지만, AI 코딩 어시스턴트에게 최적화된 형태로 재설계됐습니다. 실제 워크플로우:

- **`/generate-prp INITIAL.md`**: 코드베이스를 스캔하고 문서를 수집해 종합 PRP 청사진을 자동 생성
- **`/execute-prp PRPs/feature-name.md`**: PRP 컨텍스트를 읽고, 계획 수립 → 구현 → 자체 검증의 3단계 실행

### 3. PIV 루프 + 5개 황금 규칙

**PIV 루프(Plan → Implement → Validate)**와 5개 황금 규칙:

1. **Commandify everything** — 반복 워크플로우는 모두 재사용 커맨드로 변환
2. **Reduce assumptions** — 단계마다 가정 대신 명확한 질문
3. **Context is king** — 계획과 구현 단계를 분리
4. **Git log as memory** — 잦고 구체적인 커밋이 에이전트의 기억 자료
5. **System evolution** — 에이전트의 실수가 AI 레이어를 개선하는 피드백 루프

### 4. Archon — AI가 AI를 짓는 오픈소스 하네스

"Dockerfile이 인프라에, GitHub Actions가 CI/CD에 한 것을 AI 코딩 워크플로우에 적용한다."

### 5. 로컬 AI 스택

`local-ai-packaged` 레포: Ollama + Supabase + n8n + Open WebUI + Flowise + Neo4j + Langfuse + SearXNG를 Docker Compose 하나로 로컬에서 실행.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱 또는 ERP 레포의 루트에 `CLAUDE.md` 파일을 열고 "AI 레이어" 섹션을 추가합니다. 코드베이스 규칙 3줄, 자주 쓰는 패턴 예시 3줄, 커밋 전 자체 검증 체크리스트 3줄.

**이번 주 1-2시간 (mid)**: PRP 워크플로우를 비서앱 신기능 1개에 적용.

```bash
# .claude/commands/ 폴더에 generate-prp.md 파일 생성
mkdir -p .claude/commands
cat > .claude/commands/generate-prp.md << 'EOF'
# Generate PRP
Read INITIAL.md, analyze the codebase structure in src/, review existing patterns in examples/,
then generate a comprehensive PRP saved to PRPs/$ARGUMENTS.md.
Include: architecture decisions, code examples, validation checklist.
EOF
```

**이번 달 실험 (macro)**: ERP 개발 워크플로우 전체를 PIV 루프로 전환. 측정 지표: 첫 구현 후 수동 수정 횟수, 기능당 개발 사이클 시간.

## 한국 솔로 운영자 맥락에서 주의

**그대로 따라하면 설정에 파묻힌다.** Cole의 방법론은 정교하지만 초기 세팅 비용이 있습니다. 전체 시스템을 한 번에 도입하기보다 PRP 하나, 커맨드 하나씩 점진적으로 추가하는 것이 현실적입니다.

**185,000명 구독자 기반이 전제된 교육 사업 모델.** 방법론의 기술 핵심은 충분히 가져올 수 있지만, 콘텐츠 사업 구조를 직접 벤치마킹하려면 선행 오디언스 빌딩이 필요합니다.

## 더 깊이 보려면

- [Cole Medin GitHub — context-engineering-intro](https://github.com/coleam00/context-engineering-intro)
- [Cole Medin GitHub — Archon](https://github.com/coleam00/Archon)
- [Cole Medin YouTube Channel](https://www.youtube.com/@ColeMedin)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "AI 코딩 어시스턴트에게 시켰는데 왜 이상한 코드만 나올까요?" — 모델 탓이 아니라 컨텍스트 탓입니다.
- **숫자**: Archon GitHub 스타 13,600+개 / 유튜브 구독자 185,000명 / 컨텍스트 엔지니어링은 바이브코딩보다 100배 효과적.
- **삽질**: "AI에게 CLAUDE.md 없이 코딩 시키면 프로젝트 규칙을 전혀 모른 채 짭니다. 저도 그렇게 6개월을 날렸습니다."
- **훅**: *"당신의 AI 코딩 어시스턴트가 틀린 코드를 내놓는 이유는 AI가 멍청해서가 아닙니다. 당신이 AI에게 충분히 설명하지 않았기 때문입니다."*
