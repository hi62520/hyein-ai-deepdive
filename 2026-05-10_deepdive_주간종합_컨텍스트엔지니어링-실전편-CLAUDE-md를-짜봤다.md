---
date: 2026-05-10
category: 주간종합
subject: 컨텍스트 엔지니어링 실전편 — CLAUDE.md를 실제로 짜봤다
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱/ERP 레포 루트에 CLAUDE.md 열어서 "## Tech Stack" 섹션 하나만 추가 — 프레임워크·DB·주요 API 세 줄씩 적기
---

# 컨텍스트 엔지니어링 실전편 — CLAUDE.md를 실제로 짜봤다

## 왜 같은 주제를 다시?

목요일(5/8)에 Cole Medin의 컨텍스트 엔지니어링 철학과 PRP 프레임워크를 다뤘습니다. 핵심은 "바이브코딩은 사기, 컨텍스트 구조화가 답"이었죠. 그런데 이론은 이해했는데 실천이 막히는 순간이 있습니다. **"그래서 내 CLAUDE.md, 지금 어떻게 생겼나요?"**

이 글은 이론 복습이 아닙니다. Cole의 프레임워크를 와당탕연구소 + 느린호밀 맥락에 실제로 이식하는 방법, 즉 오늘 당장 열어서 편집할 수 있는 CLAUDE.md 실전 설계 가이드입니다. 이번 주 다룬 6개 주제 중에서 이 하나가 대표님 일상 워크플로우에 가장 직접적인 영향을 주기 때문에 일요일 재조명 주제로 골랐습니다.

## 실전 인사이트 — 이론과 구현 사이의 다섯 가지 간극

### 1. "300줄 룰" — CLAUDE.md는 짧을수록 성능이 높아진다

많은 개발자가 CLAUDE.md를 길게 쓸수록 Claude가 더 잘 이해한다고 착각합니다. 반대입니다. 2026년 Claude Code 공식 문서와 실무 사용자들의 공통 결론은 **300줄 이하, 가능하면 150줄 목표**입니다.

이유는 컨텍스트 윈도우 경쟁입니다. CLAUDE.md가 길어질수록 실제 코드·대화·도구 출력이 들어갈 자리가 줄어들고, Claude는 정작 중요한 것들을 "잊기" 시작합니다. HumanLayer의 분석에 따르면 500줄 넘는 CLAUDE.md를 쓰는 팀은 "지시는 많은데 Claude가 이상하게 행동한다"고 불평하는 경우가 잦습니다. 지시가 너무 많아서 서로 충돌하기 때문입니다.

**규칙**: CLAUDE.md에는 *코드만 봐서는 절대 알 수 없는 것*만 적는다. 예컨대 "API 키는 .env.local에 있다", "DB 스키마는 Supabase MCP로 직접 읽어라", "배포는 절대 자동으로 하지 말고 먼저 물어봐라" 같은 항목들.

### 2. 포인터를 쓰고, 코드를 복사하지 않는다

CLAUDE.md에 코드 스니펫을 직접 붙여 넣는 것은 시한폭탄입니다. 코드는 바뀌는데 CLAUDE.md는 안 바뀌어서, 6개월 후에는 Claude가 구식 패턴을 따르게 됩니다.

대신 **파일 경로 + 줄 번호 포인터**를 씁니다:

```
## 패턴 참조
- API 응답 형식: src/lib/api.ts:45-78 (표준 ApiResponse<T> 래퍼)
- DB 쿼리 패턴: src/db/queries.ts:12-30 (항상 트랜잭션으로 감쌀 것)
- 인증 미들웨어: src/middleware/auth.ts (모든 API 라우트에 적용)
```

Claude는 이 경로를 직접 읽어서 최신 코드를 컨텍스트에 가져옵니다. 코드가 바뀌어도 CLAUDE.md는 그대로 유효합니다.

### 3. examples/ 폴더가 진짜 CLAUDE.md다

Cole Medin의 context-engineering-intro 레포에서 가장 과소평가된 항목이 바로 `examples/` 폴더입니다. CLAUDE.md는 *원칙*을 적는 곳이고, examples/ 폴더는 *살아있는 패턴*을 보여주는 곳입니다.

예를 들어 와당탕 비서앱의 경우:

```
examples/
├── api-route.ts       # 올바른 Next.js API 라우트 구조
├── db-query.ts        # Prisma 쿼리 + 에러 처리 패턴
├── telegram-hook.ts   # 텔레그램 웹훅 처리 예시
└── memo-create.ts     # 메모 생성 API 전체 플로우
```

Claude에게 새 기능을 만들게 할 때 PRP(INITIAL.md)에 이렇게 적습니다: *"examples/api-route.ts 패턴을 따를 것"*. 이 한 줄이 프롬프트 500자보다 훨씬 정확한 지시입니다.

### 4. 인터뷰 퍼스트 패턴 — Claude가 먼저 물어보게 하라

가장 많이 낭비되는 컨텍스트 엔지니어링 시간은 "처음부터 Claude가 잘못된 방향으로 달려나갔을 때"입니다. 이를 막는 가장 효과적인 방법은 구현 시작 전에 Claude가 대표님을 *인터뷰*하게 만드는 것입니다.

CLAUDE.md에 이 규칙 하나를 추가하면 됩니다:

```
## 작업 시작 전 규칙
새 기능·버그픽스 요청을 받으면 바로 코드 작성 금지.
먼저 구현 방식, UI/UX, 엣지케이스, 트레이드오프에 대해
최소 3개의 명확화 질문을 해라. 답변 받은 후 계획 요약 제시.
대표님 승인 후 구현 시작.
```

이 패턴을 쓰는 팀은 "Claude가 엉뚱한 걸 만들어왔다"는 불평이 90% 이상 사라진다고 보고합니다. Claude Coding Summit 2026에서 Cole이 직접 강조한 내용이기도 합니다.

### 5. 와당탕연구소 실제 CLAUDE.md 초안 — 오늘 쓸 수 있는 템플릿

아래는 비서앱 + ERP 풀스택 개발에 바로 쓸 수 있는 CLAUDE.md 초안입니다. 총 140줄 목표로 작성했습니다.

```markdown
# 와당탕연구소 비서앱/ERP — Claude Code 규칙

## 프로젝트 개요
- 와당탕연구소(강의·컨설팅) + 느린호밀(베이커리) 운영 지원
- 비서앱: Next.js + Supabase + Telegram Bot API
- ERP: FastAPI + PostgreSQL (Supabase) + React

## Tech Stack (변경 시 여기부터 업데이트)
- Frontend: Next.js 15, TypeScript, Tailwind CSS
- Backend: FastAPI (Python), Prisma ORM
- DB: Supabase (PostgreSQL) — 스키마는 MCP로 직접 조회
- 배포: Vercel (frontend), Railway (backend)
- 인증: Supabase Auth (JWT)

## 코드 패턴 (항상 examples/ 폴더 참조)
- API 응답: examples/api-route.ts 의 ApiResponse<T> 래퍼 필수
- DB 쿼리: examples/db-query.ts — 트랜잭션 필수, 에러 로깅 포함
- 텔레그램: examples/telegram-hook.ts — webhook 검증 포함

## 절대 금지
- git push 자동 실행 — 반드시 대표님 확인 후
- DB 마이그레이션 자동 실행 — 스키마 변경은 항상 먼저 보여줄 것
- .env 파일 읽기·수정 — 환경변수는 대표님이 직접 관리
- 새 외부 라이브러리 추가 — 먼저 제안하고 승인 받을 것

## 작업 방식
1. 요청 받으면 즉시 코딩 금지. 명확화 질문 최소 2개 먼저.
2. 계획 요약 제시 → 대표님 OK 후 구현.
3. 구현 완료 후 반드시 "다음 할 일" 1개 제안.

## 환경
- API 키: .env.local (절대 코드에 하드코딩 금지)
- Supabase MCP: DB 스키마·데이터 직접 조회 가능
- 레포: github.com/hi62520/[비서앱-레포]
```

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱 또는 ERP 레포 루트를 열어서 CLAUDE.md 파일 하나 만들기. 위 템플릿에서 Tech Stack 섹션과 "절대 금지" 섹션 두 블록만 먼저 채운다. 완벽할 필요 없음. 오늘 한 세션에서 Claude에게 "이 규칙 맞냐, 빠진 게 있냐" 물어보면 Claude가 보완 제안을 해 준다.

**이번 주 1-2시간 (mid)**: examples/ 폴더 만들기. 지금까지 대표님이 가장 자주 쓰는 코드 패턴 세 가지(API 라우트, DB 쿼리, 텔레그램 메시지 전송)를 예시 파일로 정리. 실제로 잘 동작하는 코드를 복붙해서 파일로 저장하면 끝. 다음 Claude 세션부터 "examples/telegram.ts 패턴 따라서 새 명령 만들어줘"라고 하면 된다.

**이번 달 실험 (macro)**: PRP 파이프라인 도입. PRPs/ 폴더 만들고, 다음 신규 기능 하나를 INITIAL.md로 작성 → /generate-prp 실행 → 별도 세션에서 /execute-prp 실행. 기존 "그냥 말하면서 만드는" 방식과 결과물 품질·시간 비교.

측정 지표: ① Claude가 방향을 틀어서 다시 시작한 횟수 ② 기능 완성까지 걸린 총 메시지 수 ③ 버그 없이 처음 배포 성공 여부.

## 한국 솔로 운영자 맥락에서 주의

**"완벽한 CLAUDE.md 먼저 만들고 시작하겠다"는 함정**: CLAUDE.md는 한 번 완성하는 문서가 아닙니다. 오늘 20줄로 시작해서, Claude와 세션을 거듭하며 "오늘 헷갈렸던 점" 하나씩 규칙으로 추가하는 방식이 훨씬 효과적입니다. 완벽한 시작을 기다리다 영원히 안 만드는 것이 가장 나쁜 선택입니다.

**단일 레포 vs. 멀티 레포 혼용 주의**: 비서앱과 ERP가 별도 레포라면 각각 CLAUDE.md를 따로 만들어야 합니다. 그런데 두 프로젝트의 공통 규칙(절대 금지 항목, 코드 스타일)은 `~/.claude/CLAUDE.md` (글로벌)에, 프로젝트별 특수 규칙은 각 레포 루트에 두는 계층 구조를 쓰면 중복 관리 부담이 줄어듭니다.

## 더 깊이 보려면

- [coleam00/context-engineering-intro](https://github.com/coleam00/context-engineering-intro) — PRP 템플릿·슬래시 커맨드 전체 소스
- [Claude Code 공식 모범 사례](https://code.claude.com/docs/ko/best-practices) — Anthropic이 직접 정리한 CLAUDE.md 가이드
- [The Complete Claude Code Guide 2026](https://www.generative.inc/the-complete-claude-code-guide-2026-planning-context-engineering-and-high-leverage-development) — 인터뷰 퍼스트 패턴 상세 설명
- [Claude's Context Engineering Secrets](https://01.me/en/2025/12/context-engineering-from-claude/) — Anthropic 내부 관행 역공학

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "Claude Code가 내가 원하는 걸 왜 이렇게 못 알아들어?" — 알고 보면 CLAUDE.md가 없거나 500줄짜리 벽돌이었다.
- **숫자**: 300줄 이하 CLAUDE.md → 500줄 이상 대비 Claude 지시 이행률 체감 2배. 실무 사용자 커뮤니티 공통 보고.
- **삽질**: CLAUDE.md에 코드 스니펫 200줄 복붙 → 2개월 후 코드가 바뀌었는데 Claude는 구식 패턴으로 계속 구현. 포인터 하나로 해결됐을 문제.
- **훅**: "AI 코딩 어시스턴트가 멍청한 게 아니다. 당신의 CLAUDE.md가 없는 게 문제다."
