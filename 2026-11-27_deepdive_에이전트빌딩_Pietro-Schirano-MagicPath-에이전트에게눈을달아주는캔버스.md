---
date: 2026-11-27
category: 에이전트빌딩
subject: Pietro Schirano & MagicPath — 에이전트에게 눈을 달아주는 캔버스 인프라
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱 quick-action에 "npx skills add https://magicpath.ai/skill --skill magicpath" 등록 → Claude Code 세션 시작 시 한 줄로 MagicPath skill 주입 준비
---

# Pietro Schirano & MagicPath — 에이전트에게 눈을 달아주는 캔버스 인프라

## 누구/무엇인가

Pietro Schirano(@skirano)는 Anthropic 출신 엔지니어 겸 창업자로, AI 디자인·개발 멀티플레이어 캔버스 **MagicPath**의 CEO입니다. Meta, Uber, Brex를 거쳐 Anthropic 엔지니어링팀에 합류했고, 오픈소스 툴 Cloud Engineer(GitHub 별 11,000+)를 혼자 만들어 바이럴된 뒤 Anthropic에 채용된 이력을 가지고 있습니다. MagicPath는 공동창업자 Jack Beoris와 함께 Khosla Ventures 주도 $6.6M 시드 투자를 유치했습니다. 2026년 10월 ChatGPT 플러그인 출시 한 주 만에 ARR $500K를 추가했으며, OpenAI Codex·Claude Code·Cursor·Grok에 공식 플러그인으로 탑재된 첫 번째 디자인 툴입니다. 단순 AI 디자인 도구를 넘어, '에이전트가 보는 화면'을 사람과 함께 공유하는 시각 협업 인프라로 자리매김하고 있습니다.

## 무엇이 특별한가

**① 에이전트에게 눈(眼)을 달았다 — Multiplayer Canvas**

기존 AI 코딩 에이전트의 맹점은 "코드는 쓰지만 화면을 못 본다"는 것입니다. MagicPath 2.0(2026년 5월 출시)은 Codex·Claude Code·Cursor 같은 에이전트에게 무한 캔버스를 제공합니다. 에이전트가 UI 컴포넌트를 그리면 사람이 같은 캔버스에서 실시간으로 보고, 편집하고, 피드백을 줄 수 있습니다. Pietro의 발표문 원문: *"MagicPath is a multiplayer canvas for humans and agents to design and build with AI — use your codebase, grab data from anywhere, see the agents work in real time as a team."* 한국어로 의역하면, "사람과 에이전트가 같은 캔버스에서 실시간으로 함께 짓는 작업실"입니다. 에이전트가 작업하는 과정이 불투명한 블랙박스에서 투명한 공유 화면으로 바뀌는 것이 핵심 차별점입니다.

**② 플랫폼 배포가 성장 엔진이다 — 한 주 ARR $500K**

MagicPath는 2026년 한 해 Codex(OpenAI 공식 협력), ChatGPT, Cursor, Grok에 공식 플러그인으로 연이어 탑재됐습니다. 단일 AI 플랫폼에 의존하지 않고 에이전트 생태계 전체에 시각 인프라를 공급하는 전략입니다. ChatGPT 플러그인 출시 직후 한 주 만에 ARR $500K를 추가한 것은(≈ 월 $41,667 추가 반복매출), 자체 마케팅이 아니라 플랫폼 배포가 성장 엔진임을 증명합니다. Builder 플랜($10/월)은 외부 에이전트 호출 무제한에 멀티플레이어 캔버스·디자인 시스템·Figma export를 포함하며, AI 사용 비용은 에이전트 제공사(OpenAI·Anthropic 등)가 별도 청구하는 가벼운 구조입니다.

**③ Skill 아키텍처 — 에이전트를 직접 훈련시키는 명령어 한 줄**

MagicPath는 에이전트가 더 잘 작동하도록 'skill'을 주입하는 방식을 채택했습니다. 아래 한 줄로 Claude Code나 Cursor에 MagicPath 조작 능력을 심을 수 있습니다.

```bash
npx skills add https://magicpath.ai/skill --skill magicpath
```

이는 단순 API 연동을 넘어, 에이전트의 행동 방식을 명세하는 'skill 레이어' 사업 모델입니다. Pietro는 AI 랩들이 애플의 하드웨어-소프트웨어 통합 플레이북을 따라갈 것이라고 예측합니다: *"Models are the software, the harness is the hardware that lets companies sell the full experience."* (모델이 소프트웨어라면, 하네스는 경험을 파는 하드웨어다.) MagicPath의 skill이 바로 그 하네스 역할을 자임하고 있는 것입니다.

**④ 오픈소스-투-기업 경로의 교과서**

Cloud Engineer(오픈소스 AI 고객지원 에이전트)를 혼자 만들어 GitHub 별 11,000+를 받은 뒤 Anthropic에 합류한 Pietro의 커리어는 '오픈소스 바이럴 → 기업 채용 → 창업'의 현실적 경로를 보여줍니다. Anthropic 재직 중에는 RAG + Claude + AWS Knowledge Bases 기반 고객지원 에이전트를 오픈소스화해 Anthropic Cookbook에 기여하면서 MagicPath 초기 신뢰를 쌓았습니다. 기술 신뢰를 먼저 쌓고 사업으로 전환하는 패턴은, 솔로 운영자가 콘텐츠와 도구를 먼저 무료로 공개하고 나중에 유료화하는 전략과 정확히 겹칩니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱 quick-action에 `npx skills add https://magicpath.ai/skill --skill magicpath` 명령어를 등록해 두세요. Claude Code 세션을 시작할 때 MagicPath skill을 한 줄로 주입할 수 있도록 준비하는 것입니다. 대표님이 ERP 화면을 에이전트와 짤 때 '에이전트가 직접 UI를 캔버스에 그리는' 협업을 바로 실험할 수 있습니다. frontmatter의 `micro_action`과 동일합니다.

**이번 주 1-2시간 (mid)**: 느린호밀 주간 메뉴판 또는 와당탕 ERP 신규 대시보드 1개를 MagicPath Builder($10/월)에서 Claude Code와 함께 프로토타이핑해 보세요. Claude Code에게 "MagicPath 캔버스에 메뉴판 레이아웃 그려줘"라고 지시하면 에이전트가 캔버스에 직접 그리고, 대표님이 실시간으로 조정할 수 있습니다. 완성 후 Figma export → 실제 구현 코드 생성까지 파이프라인을 테스트해 보세요.

```python
# Claude Code CLAUDE.md에 추가할 MagicPath 협업 지침 예시
magicpath_workflow = """
When designing a new screen for the ERP:
1. Open MagicPath canvas (skill already installed)
2. Sketch layout with real components
3. Export to Figma or generate React code directly
4. Iterate on canvas before writing production code
"""
```

**이번 달 실험 (macro)**: 와당탕 ERP의 모든 신규 화면 설계를 "MagicPath 스케치 → Figma export → Claude Code 구현" 3단계 파이프라인으로 표준화합니다. 측정 지표 세 가지: ① 화면 1개 설계~구현 소요 시간(기존 대비), ② MagicPath 캔버스에서 에이전트가 직접 처리한 비율, ③ 디자인-코드 불일치로 인한 재작업 횟수. 3개월 데이터를 모으면 느린호밀·와당탕 2027년 AX 전환 ROI 근거 자료가 됩니다.

## 한국 솔로 운영자 맥락에서 주의

**MagicPath의 성장은 플랫폼 배포 덕분입니다.** ChatGPT·Codex·Cursor·Grok에 공식 파트너로 입점한 것은 Khosla Ventures $6.6M + OpenAI 파트너십이 있기에 가능했습니다. 한국 솔로 운영자가 비슷한 멀티플레이어 캔버스를 직접 만들어도 플랫폼 배포 채널 없이는 같은 성장 곡선을 그릴 수 없습니다. MagicPath를 '만드는 것'이 아니라 '이미 있는 MagicPath를 와당탕 개발 파이프라인에 연결하는 것'이 현실적인 적용입니다.

**Skill 아키텍처를 먼저 학습하세요.** MagicPath의 본질은 'AI 에이전트에게 skill을 주입하는 메커니즘'입니다. 대표님이 Claude Code에 CLAUDE.md와 커스텀 skill을 주입하는 현재 방식이 MagicPath의 핵심 아이디어와 동일합니다. MagicPath는 그것을 시각 캔버스에 적용했을 뿐입니다. 즉, 대표님은 이미 같은 방향으로 가고 있습니다.

## 더 깊이 보려면

- [MagicPath 공식 블로그 — Codex 플러그인 출시](https://www.magicpath.ai/blog/magicpath-official-codex-plugin)
- [Pietro Schirano @skirano (X)](https://x.com/skirano)
- [MagicPath $500K ARR 분석 — aiidelist.com](https://aiidelist.com/blog/magicpath-chatgpt-plugin-500k-arr-growth)
- [RuntimeWire — MagicPath Startup Spotlight](https://runtimewire.com/article/startup-spotlight-magicpath-pietro-schirano-s-shared-ai-native-canvas-for-human-)
- [UX Tools 인터뷰 — He Solved Figma-to-Code](https://www.uxtools.co/episodes/he-solved-figma-to-code.-it-went-viral-overnight)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "Claude Code에게 UI 짜라고 하면 코드는 나오는데 화면이 어떻게 생겼는지 모른다. 에이전트는 눈이 없다." — MagicPath가 정확히 이 고통을 겨냥합니다.
- **숫자**: ChatGPT 플러그인 출시 한 주 만에 ARR $500K 추가(≈ 월 $41,667 추가 반복매출). 플랫폼 배포 하나가 1년치 성장을 한 주에 압축한다는 것을 보여줍니다.
- **삽질**: Pietro는 Cloud Engineer 오픈소스로 GitHub 별 11,000+를 받았음에도 처음에는 바로 사업화하지 못했습니다. Anthropic 취직 후 내부에서 RAG 에이전트를 더 만들고, 그것을 다시 오픈소스화하면서 MagicPath 초기 신뢰를 쌓았습니다. '바이럴 도구 하나'가 바로 사업이 되지 않는다는 것을 직접 겪은 사례입니다.
- **훅**: "에이전트는 코드를 짤 수 있지만, 자기가 뭘 만들고 있는지 볼 수 없습니다. MagicPath는 에이전트에게 눈을 달아줬습니다."
