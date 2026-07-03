---
title: "2026-05-27; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-05-27
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - AI-LLM
  - 가족-일상
  - HRD-리더십
  - 업무자동화
  - 데이터분석
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-05-27.md"
---

# 2026-05-27; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-05-27|2026-05-27 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-05-27에는 연결 (L3), 작업 기록, OpenClaw namespace에서 병합된 기록, 연결 — OpenClaw namespace에서 병합된 기록를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 연결 (L3)

- [[Hermes]]
- [[Hermes/wiki/entities/openclaw-telegram-bots]]
- [[Hermes/daily/일지-허브]]

### 작업 기록

### Telegram memo bot 추가
- [[Hermes]] `memo` 프로필을 생성했다.
- BotFather 토큰을 `/home/brienz311/.hermes/profiles/memo/.env`의 `TELEGRAM_BOT_TOKEN`으로 설정했다.
- Telegram `getMe`로 `@Her_Chung_MemoBOT` / `Hermes_Memo` 확인.
- `tmux` 세션 `hermes-memo`에서 `/home/brienz311/.hermes/hermes-agent/venv/bin/hermes --profile memo gateway run`으로 실행했다.
- 로그에서 `Connected to Telegram (polling mode)` 및 `Gateway running with 1 platform(s)` 확인.

### OpenAI Codex GPT-5.5 TTFB 경고 억제

### OpenClaw namespace에서 병합된 기록

> Source: `/mnt/c/Obsidian/HCS/Openclaw/daily/2026-05-27.md`
> Migrated: `2026-05-27T20:57:38.205883`

### 연결 — OpenClaw namespace에서 병합된 기록

- [[Hermes/daily/일지-허브]]
- [[Hermes]]
- [[Hermes/wiki/entities/revfactory-harness]]
- [[Hermes/wiki/concepts/harness]]
- [[Hermes/wiki/concepts/agent-orchestration]]
- [[Hermes/wiki/references/codex-skills]]
- [[Hermes/wiki/entities/Bebsu]]
- [[Hermes/wiki/references/Supabase]]

### 기록

### revfactory/harness를 OpenClaw 스킬로 장착
- 충 요청: `https://github.com/revfactory/harness` 레포를 하네스 스킬로 장착.
- 작업: 원본 [[revfactory-harness]] 레포를 확인했고, Claude Code 전용 `skills/harness`를 OpenClaw/Codex용 전역 스킬 `~/.openclaw/workspace/skills/harness`로 포팅.
- 원본 자료는 `references/upstream/`에 보존하고, 활성 `SKILL.md`는 [[Hermes]] 런타임에 맞게 `AGENTS.md`, `.openclaw/harness/`, Codex subagent 정책으로 경로/실행 개념을 번역.
- 검증: `quick_validate.py` 통과, `/home/brienz311/.nvm/versions/node/v24.13.1/bin/openclaw skills check`에서 `harness`가 visible/ready 상태로 확인됨.

### Bebsu 상태 기반 장비/먹이 UI 원격 적용
- 충 요청: [[Bebsu]]에서 기본 얼굴은 밝게 유지하되 `fullness`가 낮아질수록 기력을 잃고, 먹이를 주면 다시 활성화되는 방향으로 원격 적용.

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
