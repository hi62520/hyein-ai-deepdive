---
date: 2026-06-15
category: 솔로운영자
subject: Pieter Levels — 70번 실패하고 AI로 월 5억 번다
tags: [AI탐구, deepdive]
starred: false
micro_action: 비서앱 또는 옵시디언에서 현재 운영 중인 프로젝트 목록을 만들고 각 항목에 "월 수익 목표 / 현재 수익 / kill 조건"을 3줄로 적어본다
---

# Pieter Levels — 70번 실패하고 AI로 월 5억 번다

## 누구/무엇인가

피터 레벨스(@levelsio)는 네덜란드 출신의 자기 독학 개발자이자 디지털 노마드입니다. 20대 후반에 코딩을 시작해 40개국 이상을 여행하며 40개 이상의 사이드 프로젝트를 혼자 만들었습니다. 대부분은 조용히 사라졌지만, NomadList·RemoteOK·PhotoAI·InteriorAI 같은 4개의 제품이 살아남아 2024년 9월 기준 월 $420,000(한화 약 5억 7천만 원)의 수익을 만들어냈습니다. 수익 중 80%가 이익입니다. 공동창업자도 없고, 직원도 없고, 투자도 없습니다. 서버비는 한 달에 $40~500, 전체 스택은 PHP + jQuery + SQLite 하나의 VPS 위에서 돌아갑니다.

레벨스가 특별한 이유는 단순히 "1인 기업"이어서가 아닙니다. 그는 AI를 조수 삼아 게임 개발 경력 제로의 상태에서 비행 시뮬레이터 게임을 3시간 만에 만들었고, 17일 만에 그 게임이 연 매출 $1백만(ARR $1M)을 돌파했습니다. "내가 로봇을 이끈다(I lead the robots)"는 그의 말은 허풍이 아닙니다.

## 무엇이 특별한가

### 1. 70번 실패가 포트폴리오다

레벨스는 70개 이상의 프로젝트를 출시했고 대다수가 실패했습니다. 그는 이것을 부끄럽게 여기지 않고, 오히려 **각 실패를 "다음 성공을 위한 베팅 비용"**으로 계산합니다. 살아남은 4개(PhotoAI, NomadList, RemoteOK, InteriorAI)는 서로 독립적으로 수익을 내며, 하나가 흔들려도 나머지가 버팁니다. Daniel Vassallo의 "소형 베팅 포트폴리오" 전략과 겹치지만, 레벨스의 버전은 더 공격적입니다. 실패 속도 자체가 경쟁 우위입니다.

### 2. 기술 복잡도를 의도적으로 낮춘다

PhotoAI 월 $150,000, 이익률 87%, 운영자 1명(레벨스 본인), 스택은 "PHP + jQuery + SQLite on a Hetzner VPS with Nginx and Ubuntu"입니다. 그는 2026년 기준에도 React나 Kubernetes를 쓰지 않습니다. 이유는 단 하나: **자기가 이해하지 못하는 기술에 의존하면 밤 3시에 다운된 서버를 혼자 고칠 수 없기 때문**입니다. AI 시대에 복잡성은 미덕이 아닙니다. 이해할 수 있는 코드가 유지 가능한 코드입니다.

### 3. 바이브 코딩(Vibe Coding)으로 장르를 만들었다

2025년 2월 22일, 레벨스는 브라우저 기반 3D 비행 시뮬레이터 **fly.pieter.com**을 Cursor + Claude 3.7 Sonnet + Grok 3만으로 3시간 만에 완성해 출시했습니다. 그의 X 트윗:

> "I've never ever made a game before and just made my own flight simulator 100% with Cursor in I'd say 3 hours by just telling it what I wanted."

결과: 출시 13일 차에 MRR $67,000 돌파, 17일 차에 ARR $1M($87,000 MRR). 최대 동시 접속자 31,000명, 누적 플레이어 320,000명+. 수익 모델은 게임 화면 안에 광고 블림프($1,000/주), F-16 스폰서($수천), 17개 회사 광고. 이 사례 이후 "바이브 코딩" 게임잼(jam.pieter.com)을 직접 운영하며 새로운 장르를 제도화했습니다.

### 4. 수익 공개 자체가 최강의 마케팅

레벨스는 MRR 마일스톤을 X에 반복 공개합니다. 2024년 9월의 $420K 트윗:

> "✨ I hit a new $420,000/mo revenue record 🍀 420=nice At ~80% profit now: 📸 PhotoAI $161K/m 📕 ReadMAKE $93K/m 🌍 NomadList $61K/m 🏡 InteriorAI $43K/m ..."

이 트윗들은 단순한 자랑이 아닙니다. 수치 공개 → 바이럴 → 신규 고객 인지 → 가입 증가의 루프입니다. 2024년 8월 렉스 프리드먼 팟캐스트 #440 출연 이후, 전체 매출이 2.5배, PhotoAI만 3배 올랐습니다. "빌드 인 퍼블릭"이 광고비를 대체합니다.

### 5. AI를 팀 전체로 사용한다

레벨스가 AI에 대해 말하는 핵심 프레임은 이겁니다: **"나는 CEO다. AI가 엔지니어링, 디자인, QA, 카피라이팅을 맡는다."** 그는 Cursor로 기능을 작성하고, Claude로 UX 문구를 다듬고, 이미지 생성 AI로 마케팅 에셋을 만듭니다. GPU 비용(PhotoAI·InteriorAI 합산 약 $60K/월)이 가장 큰 지출이지만, 그게 없으면 팀 10명이 필요했을 일을 혼자 합니다.

## 와당탕/느린호밀 적용 포인트

**오늘 30분 (micro)**
비서앱 또는 옵시디언에서 현재 운영 중인 프로젝트 목록을 만들고 각 항목에 "월 수익 목표 / 현재 수익 / kill 조건"을 3줄로 적어본다. 레벨스의 포트폴리오 사고를 와당탕과 느린호밀에 직접 대입해보는 5분 연습입니다.

**이번 주 1-2시간 (mid)**
Claude Code 또는 Cursor로 "72시간 출시 실험"을 하나 잡는다. ERP나 비서앱의 기능 중 가장 가파른 비용을 치르고 있는 반복 작업(예: 주문 집계, 재고 업데이트)을 고르고, 레벨스처럼 단순한 스택(PHP 없이도 Python + SQLite 또는 Node + SQLite)으로 독립 도구를 만들어 72시간 안에 첫 사용자(=본인)에게 배포한다.

```python
# 느린호밀 주문 집계 예시 — SQLite 한 파일로 시작
import sqlite3, datetime

conn = sqlite3.connect("rye_orders.db")
conn.execute("""CREATE TABLE IF NOT EXISTS orders (
    id INTEGER PRIMARY KEY,
    item TEXT,
    qty INTEGER,
    price REAL,
    created_at TEXT
)""")
# 레벨스 원칙: 이 파일 하나가 전부. 복잡해지면 나중에 분리.
```

**이번 달 실험 (macro)**
"kill 조건"을 미리 정해두는 실험. 와당탕 비서앱이나 ERP에서 신규 기능 하나를 붙일 때, 30일 내 사용 횟수 기준 kill 조건을 명시하고 실제로 실행한다. 레벨스가 70개 프로젝트를 빠르게 종료할 수 있었던 이유는 "언제 그만둘지"를 시작 전에 정해뒀기 때문입니다.

## 한국 솔로 운영자 맥락에서 주의

**1. "빌드 인 퍼블릭"은 신뢰 축적 없이는 역효과입니다.** 레벨스는 10년 넘게 온라인에서 활동하며 쌓은 팔로워 기반이 있습니다. 한국 소규모 B2B SaaS(예: 와당탕 ERP) 맥락에서는 MRR 공개가 오히려 고객사가 "우리 데이터가 안전한가?"를 걱정하게 만들 수 있습니다. 공개할 수치는 "성장률"보다 "안정성 지표"로 선별하는 편이 낫습니다.

**2. PHP + SQLite 원칙을 맹목적으로 따르면 안 됩니다.** 레벨스의 단순 스택은 그가 혼자 10년 넘게 유지해온 것이고, 그 스택의 한계(멀티테넌시, 동시 쓰기)를 그는 본능적으로 알고 우회합니다. 대표님처럼 Claude Code로 빠르게 구현할 때는 SQLite가 맞는 경우도 있지만, ERP처럼 여러 계정이 동시 접속하는 서비스는 처음부터 PostgreSQL을 고르는 것이 더 레벨스답습니다.

## 더 깊이 보려면
- [levelsio X(트위터) — 수익 공개 스레드 모음](https://x.com/levelsio)
- [Lex Fridman Podcast #440 — Pieter Levels](https://lexfridman.com/pieter-levels/)
- [fly.pieter.com — 직접 플레이해보기](https://fly.pieter.com)
- [Indie Hackers — PhotoAI $0→$132K MRR 케이스스터디](https://www.indiehackers.com/post/photo-ai-by-pieter-levels-complete-deep-dive-case-study-0-to-132k-mrr-in-18-months-3a9a2b1579)

## 강의 메모 후보 (Pain/숫자/삽질/훅)

- **Pain**: "아이디어가 나쁜 게 아니다. 하나에 집착해서 kill을 못 하는 게 나쁜 것이다." — 70번 실패한 사람의 진단.
- **숫자**: fly.pieter.com — 게임 개발 경력 0년, 코딩 3시간, 17일 만에 ARR $1M($87,000 MRR). 2025년 최고 동시 접속 31,000명.
- **삽질**: PhotoAI는 처음 이미지 생성에 Stable Diffusion을 직접 돌렸다가 GPU 비용 폭탄을 맞고 외부 API로 전환. "내가 이해하는 것만 직접 운영한다"는 원칙이 여기서 나왔음.
- **훅**: "게임을 만들어본 적 없는 사람이 AI한테 3시간 동안 시켜서 만든 게임이 17일 만에 연 매출 12억을 찍었습니다. 이게 솔로 운영자한테 무슨 의미냐면—"
