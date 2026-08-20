---
date: 2026-08-21
category: 에이전트빌딩
subject: Pietro Schirano — 인간과 에이전트가 함께 설계하는 멀티플레이어 캔버스
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱 신규 기능 하나를 MagicPath 무료 플랜에 프롬프트로 넣어 UI 시안 1개 생성, 코드 추출해 ERP 컴포넌트 폴더에 저장
---

# Pietro Schirano & MagicPath 2.0 — 인간과 에이전트가 같은 캔버스 위에서 설계한다

## 누구/무엇인가

Pietro Schirano(@skirano)는 핵공학도 출신의 이탈리아계 AI 파운더입니다. OpenTable → Facebook → Uber → Brex → Anthropic을 거친 뒤 2025년 5월 MagicPath를 창업했습니다. Anthropic 재직 시절 그가 오픈소스로 공개한 CLI 툴 **Claude Engineer**는 GitHub에서 11,000개 이상의 스타를 받았고, Anthropic의 MCP 프레임워크 초기 서버 구축에도 참여했습니다. MagicPath는 창업 직후 Khosla Ventures와 Abstract VC 주도로 **$6.6M 시드 라운드**를 마감했습니다.

2026년 5월 MagicPath 2.0을 공개했고, 같은 해 6월에는 OpenAI Codex의 **공식 플러그인**으로 선정됐습니다. 대표님이 이미 아시는 "디자이너가 AI 아키텍트로 승진하는 법"의 그 Pietro입니다. 이번 딥다이브는 1.0 이후 가장 결정적인 변화인 **멀티플레이어 에이전트 캔버스**를 집중 해부합니다.

## 무엇이 특별한가

### 1. "인간 + 에이전트"가 동시에 같은 캔버스를 편집한다

MagicPath 2.0 런칭 트윗에서 Pietro는 이렇게 정의했습니다.

> "MagicPath is now a multiplayer canvas for humans and agents like Codex or Claude Code to design and build with AI. Use your codebase, grab data from anywhere, and see the agents work in real time as a team while building fully functional prototypes."

이전 AI 디자인 툴은 "AI가 생성 → 인간이 수정"이라는 순차 구조였습니다. 2.0은 이 구조를 깨고 Codex나 Claude Code 같은 코딩 에이전트와 인간 디자이너가 **동시에 같은 캔버스를 편집**합니다. AI가 컴포넌트를 만드는 동안 사람은 옆에서 레이아웃을 조정하고, AI는 실시간으로 반영합니다. '리뷰-승인' 병목 없이 루프가 돌아갑니다.

### 2. 생성 속도 40% 향상 + 에러율 8% 개선 — 수치가 공개된 이유

Pietro는 성능 업데이트에서 구체적 수치를 공개합니다.

> "Generation speeds are now 40% faster. Time-to-first-token improved 10%, error rate down 8% per our eval harness."

솔로 창업자가 벤치마크 수치를 공개하는 행위 자체가 신뢰 자산입니다. "eval harness를 직접 돌린다"는 표현은 내부 품질 기준이 있다는 신호이기도 합니다. 대표님의 비서앱·ERP 개발에서도 기능 릴리스마다 실행 시간 또는 오류율을 하나라도 비교하면 사용자 신뢰가 쌓입니다.

### 3. OpenAI Codex 공식 플러그인 — 에이전트 생태계 내 포지션 획득

2026년 6월 5일, MagicPath는 Codex의 공식 플러그인이 됐습니다.

> "MagicPath is now an official plugin for Codex, in collaboration with OpenAI. It's incredibly easy to give Codex an infinite multiplayer canvas where it can design, build, and iterate with you."

Claude Code가 MCP로 외부 툴을 연결하듯, Codex가 MagicPath 캔버스를 직접 호출합니다. "Codex가 무엇을 설계할지 결정하고, MagicPath가 실제로 그린다"는 구조입니다. Pietro 본인은 Claude Code 사용을 완전히 중단하고 Codex + MagicPath 조합으로 이행했다고 트윗했습니다. 플랫폼 간 유통 경쟁에서 에이전트 생태계 내 표준 플러그인 자리를 차지한 사례입니다.

### 4. "바이브 디자이닝"과 Design Architect 테제

Pietro의 핵심 주장을 요약하면 두 문장입니다.

- "AI is not replacing designers. AI just gave designers a promotion."  
- 미래의 최고 보수 직군은 '픽셀을 만드는 디자이너'가 아닌, **AI 팀 전체를 지휘하는 Design Architect**다.

"바이브 코딩(vibe coding)"이 자연어 의도로 코드를 쓰듯, **"바이브 디자이닝(vibe designing)"**은 자연어 의도로 UI를 설계합니다. 출력은 Figma 파일이 아닌 **프로덕션 React/Tailwind 코드**입니다. 이 포지셔닝은 Figma 생태계에 머무는 다른 디자인 툴과 근본적으로 다른 진입점입니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: MagicPath 무료 플랜(magicpath.ai)에서 비서앱이나 ERP 기능 중 신규 화면 1개를 자연어로 프롬프트. "와당탕 공구 주문 등록 폼, 모바일, 점진적 입력 스텝, 한국 ERP 스타일"처럼 맥락을 담아 입력 → React 코드 추출 → ERP `/components` 폴더에 저장해두기. (micro_action과 동일)

**이번 주 1-2시간 (mid)**: MagicPath의 MCP 서버를 Claude Code 프로젝트에 연결합니다. `claude_mcp_config.json`에 MagicPath MCP 엔드포인트를 추가하면 Claude Code가 직접 MagicPath 캔버스를 호출합니다. 비서앱에서 "이 기능 UI 시안 뽑아줘"라고 말하면 Claude Code → MagicPath → 코드 반환 루프가 자동화됩니다. 스니펫 예시:

```json
{
  "mcpServers": {
    "magicpath": {
      "command": "npx",
      "args": ["-y", "@magicpath/mcp-server"],
      "env": { "MAGICPATH_API_KEY": "<your-key>" }
    }
  }
}
```

**이번 달 실험 (macro)**: 와당탕연구소 온라인 강의 신규 회차 랜딩 페이지 제작 파이프라인을 MagicPath로 전환합니다. 측정 지표: ① 랜딩 초안 생성 시간(목표: 2시간 → 30분), ② Figma 없이 개발자 넘기기까지 소요 단계 수(목표: 5단계 → 2단계). 결과를 비서앱 memo로 기록해 다음 강의 커리큘럼 근거로.

## 한국 솔로 운영자 맥락에서 주의

**1. 에이전트 캔버스는 아직 Codex 생태계 중심입니다.** MagicPath 2.0의 멀티플레이어 기능은 Codex 공식 플러그인을 기반으로 설계됐습니다. Claude Code 연동은 MCP 서버를 통해 가능하지만 Codex 수준의 네이티브 통합은 아닙니다. 대표님처럼 Claude Code 기반으로 풀스택 개발 중이라면 MCP 서버 방식이 현실적 접근이지만, Codex와 같은 "실시간 공동 편집" 경험은 아직 제한적입니다. 기능을 맹신하기 전에 Claude Code MCP 연결 테스트를 먼저 진행하세요.

**2. MagicPath 출력은 Figma가 아닌 코드입니다.** 와당탕 콘텐츠팀이나 외주 디자이너가 Figma 기반이라면 MagicPath 도입 시 협업 포맷 충돌이 생깁니다. 내부에서 대표님 혼자 개발하는 ERP·비서앱 UI에는 바로 투입 가능하지만, 외부 협력자가 있는 프로젝트에는 중간 변환 단계가 필요합니다.

## 더 깊이 보려면

- [MagicPath 공식 사이트](https://magicpath.ai)
- [Pietro의 MagicPath 2.0 발표 트윗](https://x.com/skirano/status/2054975534539370708)
- [Codex 공식 플러그인 발표 트윗](https://x.com/skirano/status/2062942695547375829)
- [Dive Club 팟캐스트: "AI just gave designers a promotion"](https://www.youtube.com/watch?v=Eqvgx_9RcW8)
- [UX Tools 인터뷰 (2026년 2월): "He Solved Figma-to-Code. It Went Viral Overnight."](https://www.uxtools.co/episodes/he-solved-figma-to-code.-it-went-viral-overnight)
- [Maven 강의: From Designer to Design Architect with MagicPath](https://maven.com/p/462213/from-designer-to-design-architect-with-magic-path)
- [Claude Engineer (오픈소스 CLI, GitHub 11K+ stars)](https://github.com/doriandarko)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: 솔로 개발자가 UI 하나 만들려면 Figma → 디자이너 의뢰 → 수정 → 코드 변환 — 최소 3일. MagicPath 2.0은 이 루프 전체를 30분으로 압축합니다.
- **숫자**: 생성 속도 40% 향상, $6.6M 시드 조달, GitHub Claude Engineer 11,000+ 스타 — 제품이 아닌 오픈소스가 먼저 신뢰를 만들었습니다.
- **삽질**: Pietro는 Figma MCP와 Chrome 확장 두 단계를 요구하는 1.0 구조의 마찰을 인정하고 2.0에서 완전히 재설계했습니다. "복잡한 온보딩이 전환율을 죽인다"는 전형적인 B2B SaaS 교훈.
- **훅**: "AI가 당신을 대신해 UI를 그리는 게 아닙니다. AI가 당신과 함께 같은 캔버스 위에서 **동시에** 그립니다. 당신이 레이아웃을 잡는 동안 에이전트는 컴포넌트를 채웁니다. 이 차이가 10배의 속도를 만듭니다."
