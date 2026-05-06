---
date: 2026-05-07
category: 시스템·방법론
subject: Steph Ango — 파일이 앱보다 오래 산다
tags: [AI탐구, deepdive]
starred: false
micro_action: 옵시디언 볼트 루트에 .claude 폴더를 만들고, github.com/kepano/obsidian-skills 에서 README 읽은 뒤 obsidian-markdown.md 스킬 파일 1개만 추가해 Claude Code 세션에서 /vault list 테스트
---

# Steph Ango — 파일이 앱보다 오래 산다

## 누구인가

Steph Ango(@kepano)는 노트 앱 Obsidian의 CEO입니다. 원래는 열성 사용자였다가 공동창업자 팀에 합류해 1.0 출시 직전 CEO 자리를 맡았습니다. 배경은 생물학 + 산업디자인이고, 그 이전에는 Lumi(패키징 인쇄 플랫폼)를 공동창업해 YC를 거쳤습니다. 개발자가 아닌 디자이너·에세이스트·툴메이커로 자신을 소개하며, stephango.com에 500단어 이하 에세이를 꾸준히 발행합니다. X에서는 @kepano로 활동하고 Obsidian 외에도 다양한 오픈소스 플러그인과 테마를 직접 만듭니다. 2026년 현재 Obsidian은 전 세계 월 150만 명 이상이 사용하고 있으며, 팀 인원은 단 7명입니다.

## 무엇이 특별한가

### 1. "File over app" — 데이터 주권 선언

"If you want to create digital artifacts that last, they must be files you can control, in formats that are easy to retrieve and read."
("오래 남는 디지털 결과물을 만들고 싶다면, 반드시 내가 통제할 수 있는 파일이어야 한다. 쉽게 꺼내 읽을 수 있는 형식으로.")

2023년에 발행한 이 한 편의 에세이가 Obsidian의 핵심 철학을 집약합니다. 앱은 언젠가 종료되고, 구독은 끊기고, 서버는 닫힙니다. 하지만 내 로컬 폴더에 있는 마크다운 `.md` 파일은 10년 뒤에도 텍스트 편집기 어디서나 열립니다. "In the fullness of time, the files you create are more important than the tools you use to create them." ("결국 중요한 것은 도구가 아니라 당신이 만든 파일이다.") Notion·Roam·베어 등 클라우드 노트 앱이 폭발적으로 성장하던 시기에, 정반대 방향의 철학으로 150만 유저를 끌어모은 역주행 사례입니다.

### 2. 7인 팀·$25M ARR·VC 없음 — 솔로프레너십의 극단

Obsidian은 2025~2026 기준 연간 반복 매출(ARR) 약 2,500만 달러를 7명이 만들어냅니다. 기업 가치는 $350M 추정. 벤처캐피탈 투자 없음, 사용자 데이터 수집 없음, 내부 미팅 없음(회의 대신 '램블링'이라는 비동기 텍스트 스트림으로 소통). Ango는 팀 규모 상한선을 10~12명으로 선언했습니다. 이유는 단순합니다. "That's the maximum number where you don't need a management layer — everyone is a direct contributor." ("관리자 레이어 없이 모두가 직접 기여자로 남을 수 있는 최대치다.") 이 구조는 SaaS '성장 최우선' 패러다임에 대한 의도적 거부이며, 1인 운영자에게 "스케일 안 해도 된다"는 강력한 반례입니다.

### 3. obsidian-skills — AI 에이전트에게 볼트 쓰는 법을 가르치다

2026년 초, Ango는 `kepano/obsidian-skills`를 GitHub에 공개했습니다. 현재 29,000개 이상의 스타를 받은 이 레포는 Claude Code·Codex CLI·Gemini CLI 등 Agent Skills 스펙 호환 에이전트에게 Obsidian의 마크다운 방언, Bases(데이터베이스 뷰), JSON Canvas, CLI를 가르치는 스킬 파일 모음입니다. 설치 방법은 간단합니다. Obsidian 볼트 루트에 `.claude/` 폴더를 만들고 레포 내용을 넣으면 끝. 그 순간부터 Claude Code가 볼트 구조를 이해하고 노트 생성·편집·링크·태그 관리를 직접 수행합니다. "Instead of adding an 'Ask AI' button to the UI, we released an open-source repo that teaches AI how to use Obsidian properly." ("UI에 'AI에게 물어보기' 버튼을 달지 않고, AI가 Obsidian을 제대로 쓰는 법을 가르치는 오픈소스 레포를 냈습니다.") 이는 AI 통합에서 UI 중심이 아닌 에이전트 중심 접근법의 교과서적 사례입니다.

### 4. "Quality software deserves your hard-earned cash" — 돈 내라는 선언

Ango는 또 다른 에세이에서 "독립 개발자가 만든 좋은 소프트웨어는 파머스마켓의 수제 유기농 잼과 같다"고 비유합니다. 대기업의 프리미엄 덤핑에 맞서 지속 가능한 소프트웨어 생태계를 만들려면 사용자가 가치에 돈을 내야 한다는 주장입니다. Obsidian 자체가 이 논리로 운영됩니다. 기본 개인 사용은 무료, 상업·동기화·퍼블리시 기능은 유료. 복잡한 프리미엄 게이팅 없이 신뢰로 매출을 만드는 구조입니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 옵시디언 볼트 루트에 `.claude/` 폴더를 만들고, `github.com/kepano/obsidian-skills` 에서 README를 읽은 뒤 `obsidian-markdown.md` 스킬 파일 1개만 복사해 넣기. 그 다음 Claude Code를 볼트 루트에서 열어 "와당탕연구소 프로젝트 목록 노트 만들어줘" 한 마디 테스트. `frontmatter`의 `micro_action` 과 동일.

**이번 주 1-2시간 (mid)**: obsidian-bases 스킬까지 추가하고 비서앱 ERP의 클라이언트 목록을 Obsidian Bases 뷰로 연동. Claude Code에게 "이번 달 미팅 없는 클라이언트 필터링해서 follow-up 노트 초안 만들어줘" 명령 프롬프트 작성. 코드 스니펫 예시:

```
# .claude/CLAUDE.md (볼트 루트)
이 볼트는 와당탕연구소 + 느린호밀 second brain입니다.
프로젝트 노트: /Projects/
클라이언트: /CRM/
강의 자료: /Courses/
에이전트가 파일 생성 시 반드시 frontmatter에 date, tags 포함.
```

**이번 달 실험 (macro)**: "파일 우선 CRM" 파일럿. 외부 CRM 없이 Obsidian 볼트 + Claude Code로 클라이언트 노트·미팅 기록·follow-up 일정 전부 관리. 성공 기준: 한 달 뒤 외부 SaaS 없이 CRM 기능 100% 대체 여부, Claude Code가 "이번 주 연락 안 한 클라이언트 리스트" 질문에 정확히 답변하는지.

## 한국 솔로 운영자 맥락에서 주의

**도구 철학에만 빠지지 말 것**: "파일이 앱보다 오래 산다"는 진리지만, 볼트 구조 최적화와 스킬 파일 설정에 시간을 쏟다 보면 정작 콘텐츠 생산이 뒤로 밀립니다. 시스템은 일주일에 30분 이내로만 건드리고, 나머지는 실제 글·강의·고객 대응에 써야 합니다. Ango 본인도 "시스템이 아니라 아웃풋이 증거"라고 강조합니다.

**한국 비즈니스 맥락의 데이터 이동성 한계**: 클라이언트 계약서·세금계산서 등 법적 문서는 로컬 마크다운만으로 관리하면 공유·서명·보관 요건을 충족 못 합니다. "파일 우선" 원칙은 사고(思考)와 지식 관리에 적용하되, 법무·회계는 기존 SaaS(세금계산서 앱, 전자계약 서비스)와 병행해야 합니다.

## 더 깊이 보려면

- [File over app 원문 — stephango.com](https://stephango.com/file-over-app)
- [kepano/obsidian-skills GitHub](https://github.com/kepano/obsidian-skills)
- [Obsidian Skills Review 2026 — vibecoding.app](https://vibecoding.app/blog/obsidian-skills-review)
- [Three Engineers, Zero Financing, No Meetings — 36kr English](https://eu.36kr.com/en/p/3755031628005892)
- [Dialectic Podcast Ep.8 — Steph Ango](https://jacksondahl.com/dialectic/steph-ango)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: Notion 3년 썼더니 내보내기가 Notion 전용 HTML 덩어리. 다른 앱으로 옮기는 데 사흘. 노트 앱을 바꿀 때마다 지식이 인질로 잡힌다.
- **숫자**: 7명 팀 · $25M ARR · $350M 기업가치 · VC 투자 0원 · 내부 미팅 0회 · 월간 활성 유저 150만. 인당 매출 $3.5M.
- **삽질**: Ango가 obsidian-skills를 UI 버튼으로 넣지 않고 오픈소스 레포로 출시한 이유는 "앱 안에 AI를 가두면 우리 철학(파일 우선)을 스스로 깨는 것"이었기 때문. 처음엔 플러그인으로 만들려다 방향 전환.
- **훅**: "당신이 지금 쓰는 노트 앱이 내년에 망하면, 당신의 5년 치 생각은 어디 있습니까?"
