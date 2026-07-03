---
title: "2026-06-14; 나는 몸의 반응을 관찰하며 생활 리듬을 기록했다"
date: 2026-06-14
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - 자기돌봄
  - 건강기록
  - 가족-일상
  - Hermes
  - 인프라-도구
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-06-14.md"
---

# 2026-06-14; 나는 몸의 반응을 관찰하며 생활 리듬을 기록했다

## 연결

- [[Hermes/daily/2026-06-14|2026-06-14 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-06-14의 기록은 몸의 반응을 관찰하고 생활 리듬과 연결해 해석하려는 시도였다. 복용 이후의 컨디션 변화를 단정하지 않고, 수면량과 일상 리듬이라는 주변 조건까지 함께 보려 했다. 이 날의 의미는 문제를 즉시 결론내리기보다, 반복 관찰이 가능한 형태로 남겼다는 데 있다.

## 기록에서 건진 것

### 작업 기록

### 14:38 Telegram 챗봇별 세션 매핑 및 macOS-only guard 적용
- 요청: [[Hermes]] Telegram 챗봇별 세션을 정확히 매핑하고 Mac 환경에서만 동작하도록 정리.
- 확인: MacBook `01chungee10ui-MacBookPro.local` / macOS Darwin에서 `default`, `img`, `learn`, `memo`, `scheduler`, `try`, `family`, `work`, `research` 게이트웨이와 Telegram bot `getMe` 결과를 대조.
- 산출물:
  - `/Users/01chungee10/.hermes/profiles/research/telegram_bot_session_map.md`
  - `/Users/01chungee10/.hermes/profiles/research/telegram_bot_session_map.json`
- 적용: `/Users/01chungee10/.hermes/scripts/hermes-gateway-macos-only.sh` 생성. LaunchAgent plist의 `ProgramArguments`를 wrapper 경유로 변경하고 `HERMES_EXPECTED_HOST=01chungee10ui-MacBookPro.local` 추가.
- 백업: `/Users/01chungee10/.hermes/backups/launchagents-macos-only-20260614T143505`

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
