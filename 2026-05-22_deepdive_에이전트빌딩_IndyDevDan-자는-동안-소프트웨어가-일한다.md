---
date: 2026-05-22
category: 에이전트빌딩
subject: IndyDevDan — 자는 동안 소프트웨어가 일한다
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱 CLAUDE.md를 열고 현재 에이전트 역할 목록을 작성한 뒤 "One agent, one purpose" 원칙에 따라 분리 가능한 역할 1개에 코멘트 달기
---

# IndyDevDan — 자는 동안 소프트웨어가 일한다

## 누구/무엇인가

Dan Isler, GitHub 핸들 `disler`, YouTube 채널명 IndyDevDan. 소프트웨어 엔지니어로 15년 이상의 현장 경력을 가졌고, 현재는 **agenticengineer.com**을 운영하며 "에이전트 엔지니어" 개념을 전파하고 있습니다. YouTube 누적 조회수 2M+를 기록했으며, 유료 코스 두 개(Principled AI Coding, Tactical Agentic Coding)를 직접 판매합니다. 코스를 SaaS로 포장하지 않고 자신의 도메인에서 직접 판매한다는 점에서 전형적인 AI-네이티브 솔로프레너 구조입니다. 2026년 5월 11일에 "Tactical Agentic Coding(TAC)"을 대규모 업데이트했고, 동시에 `agentic-drop-zones`, `infinite-agentic-loop` 등 오픈소스 프로젝트를 꾸준히 공개하며 이론을 코드로 증명합니다. 그의 선언은 단 한 문장으로 압축됩니다: **"Agentic engineers build software that works for them while they sleep."**

## 무엇이 특별한가

### 1. "Living Software" 테제 — 소프트웨어를 살아 있는 존재로 정의

IndyDevDan이 사용하는 핵심 용어는 **Living Software(살아 있는 소프트웨어)**입니다. 일반적으로 소프트웨어는 "명령받으면 실행되는 것"이지만, 그는 이를 뒤집습니다.

> *"When you become an agentic engineer you will design and build systems that generate outcomes, on your behalf, while you sleep. When you wake, your teams of agents will prompt you for input for current and new tasks then go back to work for you while you do whatever you want."*

(에이전트 엔지니어가 되면, 당신이 잠든 사이에 결과를 만들어내는 시스템을 설계·구축하게 됩니다. 아침에 일어나면 에이전트 팀이 현재 태스크와 새 태스크에 대한 입력을 요청하고, 그 후 당신이 무엇을 하든 상관없이 다시 일하러 돌아갑니다.)

소프트웨어가 사람을 돕는 것이 아니라, 사람이 소프트웨어 팀의 **CEO**가 되는 구조입니다. 솔로프레너에게 이 프레이밍은 매우 강력합니다.

### 2. PITER 모델 — 멀티에이전트 오케스트레이션의 구체적 청사진

단순히 "멀티에이전트 써라"가 아닙니다. PITER 모델은 개발자 워크플로우를 **수동 상호작용 → 완전 자율 에이전트 시스템**으로 단계적으로 전환시키는 프레임워크입니다. 실제 사용 사례로, Principal Engineer Ahmed Haque가 PITER 모델을 도입해 기존 멀티에이전트 배포 시간을 **60% 단축**한 것이 공개되어 있습니다. 프레임워크에는 6개 "Agentic Horizon" 모듈이 포함됩니다: Elite Context Engineering, Agentic Prompt Engineering, Domain-Specific Agents, Multi-Agent Orchestration(PITER), Agent Experts, Codebase Singularity.

### 3. 12 Leverage Points — 에이전트 자율성 스택

에이전트가 혼자 잘 작동하게 만들려면 단순히 프롬프트를 잘 쓰는 것 이상이 필요합니다. IndyDevDan은 **12개의 레버리지 포인트**를 제시합니다. 핵심은 standard output 포맷 정의, 타입 명세, 테스트 자동화, 아키텍처 설계 등을 **쌓는(stacking)** 것입니다. 하나씩 추가할 때마다 에이전트가 더 멀리 자율로 달릴 수 있는 구조가 됩니다. 레버를 다 쌓으면 **AFK(Away From Keyboard) Agent** — 즉 사람이 자리를 비워도 스스로 계획·실행·자기수정하는 에이전트가 가능해집니다.

### 4. Closed-Loop Prompting — 에러를 자동으로 잡아 되먹이는 구조

"에이전트가 실수했다 → 사람이 고친다 → 다시 실행"의 루프에서 탈출하는 방법이 Closed-Loop Prompting입니다. 에이전트 파이프라인 안에 검증 스텝을 내장해, 에러 발생 시 결과물을 다시 입력으로 넣어 스스로 수정하게 합니다. 이것이 ZTE(Zero Touch Execution) 프레임워크와 결합될 때, 인간 개입 없이 완료되는 태스크 비율이 극적으로 높아집니다.

### 5. 오픈소스로 증명하는 방식

강의만 팔고 끝내는 게 아닙니다. GitHub(`github.com/disler`)에 실제 작동하는 프로젝트를 공개합니다.

- **`agentic-drop-zones`**: 폴더를 모니터링하다가 파일이 드롭되면 Claude Code / Gemini CLI / Codex CLI 중 하나를 자동 트리거. 단일 Python 파일 + YAML 설정 구조로 설계 복잡도가 매우 낮습니다. "Watch → Match → Process → Output" 4단계 파이프라인.
- **`infinite-agentic-loop`**: 슬래시 커맨드 하나로 에이전트 1개, 5개, 20개, 무한 모드를 선택해 병렬 실행. 콘텐츠 생성·코드 생성에 바로 적용 가능한 패턴.
- **`claude-code-hooks-multi-agent-observability`**: Claude Code 에이전트들의 활동을 실시간으로 모니터링하는 훅 시스템.

이 프로젝트들은 모두 "베껴서 쓸 수 있는" 수준으로 구현되어 있습니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**: 비서앱 CLAUDE.md를 열고 현재 에이전트가 맡고 있는 역할 목록을 나열합니다. "One agent, one purpose" 원칙으로 역할이 2개 이상 섞인 에이전트 1개를 찾아 `# TODO: 분리 필요 — [역할A], [역할B]` 코멘트를 달아두세요. 실행까지 안 해도 됩니다. 진단만으로 다음 스프린트 방향이 잡힙니다.

**이번 주 1-2시간 (mid)**: `agentic-drop-zones` 패턴으로 비서앱에 "인박스 폴더 감지 → 자동 요약" 흐름 1개를 만들어보세요. 핵심은 단순함입니다.

```python
# inbox_agent.py — 파일 드롭 감지 후 Claude 에이전트 실행
import watchdog.events, watchdog.observers, subprocess, time

class DropHandler(watchdog.events.FileSystemEventHandler):
    def on_created(self, event):
        if not event.is_directory:
            subprocess.run([
                "claude", "-p",
                f"파일 {event.src_path}를 읽고 핵심 내용을 3줄로 요약하라. "
                "결과를 ./summaries/ 폴더에 같은 파일명.txt로 저장하라.",
                "--allowedTools", "Read,Write",
            ])

obs = watchdog.observers.Observer()
obs.schedule(DropHandler(), path="./inbox", recursive=False)
obs.start()
try:
    while True: time.sleep(1)
except KeyboardInterrupt:
    obs.stop()
```

`./inbox`에 파일을 드롭하면 Claude가 자동 요약을 `./summaries/`에 씁니다. 옵시디언 vault 안에 이 폴더 구조를 두면 자동 노트 생성으로 확장됩니다.

**이번 달 실험 (macro)**: Closed-Loop Prompting을 ERP의 한 태스크(예: 월별 지출 카테고리 분류)에 적용합니다. 에이전트가 분류 → 검증 스크립트로 이상값 감지 → 이상값 있으면 재분류 루프를 돌도록 설계합니다. 측정 지표: "사람 개입 없이 완료된 분류 수 / 전체 항목 수". 목표는 80% 이상.

## 한국 솔로 운영자 맥락에서 주의

**1. "중급 이상 엔지니어" 가정 문제**: TAC 코스는 Git, TypeScript, Python, Docker 모두 능숙한 시니어 개발자 전제로 설계되어 있습니다. 대표님처럼 Claude Code를 주력으로 쓰면서 풀스택을 혼자 빌딩하는 경우, 유료 코스 수강보다 GitHub 오픈소스 프로젝트와 YouTube "Claude Code Deep Mastery" 플레이리스트를 먼저 소화하는 것이 ROI가 높습니다.

**2. 한국어 Closed-Loop 설계**: IndyDevDan의 검증 루프 예시는 대부분 영어 도메인 기준입니다. ERP에서 세무·회계 용어(부가세, 손익계산서, 매입매출 구분)를 다루는 Closed-Loop를 만들 때는 자기수정 기준(assertion 조건)을 한국어로 별도 명세해야 합니다. 그렇지 않으면 에이전트가 "맞게 고쳤다"고 판단하는 기준이 흔들려 루프가 발산합니다.

## 더 깊이 보려면

- [agenticengineer.com — Tactical Agentic Coding](https://agenticengineer.com/tactical-agentic-coding)
- [GitHub: disler — 오픈소스 에이전트 프로젝트 모음](https://github.com/disler)
- [YouTube: IndyDevDan — Claude Code Deep Mastery 플레이리스트](https://www.youtube.com/@indydevdan/videos)
- [agentic-drop-zones](https://github.com/disler/agentic-drop-zones)
- [infinite-agentic-loop](https://github.com/disler/infinite-agentic-loop)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "에이전트를 만들었는데 내가 계속 감시해야 하면, 자동화가 아니라 그냥 내 일이 하나 더 늘어난 겁니다."
- **숫자**: PITER 모델 도입 → 멀티에이전트 배포 시간 **60% 단축** (Ahmed Haque, Principal Engineer 실사례). `infinite-agentic-loop`은 슬래시 커맨드 1개로 에이전트 **최대 20개 병렬 실행** 지원.
- **삽질**: 에이전트 하나에 역할을 3개 이상 몰아넣으면 컨텍스트가 오염되고 Closed-Loop 자기수정이 오히려 에러를 **증폭**시킨다. "One agent, one purpose" 위반의 가장 흔한 실패 패턴.
- **훅**: "밤에 자는 동안 에이전트가 일을 끝내 두면, 아침에 당신이 할 일은 에이전트가 쌓아 놓은 결과를 검토하는 것뿐입니다. 그게 Living Software입니다."
