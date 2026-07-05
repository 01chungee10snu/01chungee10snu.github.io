---
title: "2026-06-22; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-06-22
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - AI-LLM
  - 업무자동화
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-06-22.md"
---

# 2026-06-22; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-06-22|2026-06-22 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-06-22에는 작업 기록를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 작업 기록

- [[Hermes/Hermes]] 챗봇 후속 작업 감지(2026-06-21 21:44, `try/telegram`, session `20260621_150853_7991eb`): Jump Desktop을 통해서 맥북에 접속할 수 있도록 세팅해줘 맥 패스워드는 peonybom0923 이야. 요청 내용: “Jump Desktop을 통해서 맥북에 접속할 수 있도록 세팅해줘 맥 패스워드는 peonybom0923 이야”; “[System note: Your previous turn in this session was interrupted by a gateway shutdown. The conversation history below…”; “[Replying to: "완료됐습니다. 정리합니다. @Hermes\_ZAIBOT(zai 프로필) Qwen 전환 완료 - 모델: gpt-5.5 → qwen3-coder (Nous Portal 경유) - Qwen O…”
- [[Hermes/Hermes]] 챗봇 후속 작업 감지(2026-06-21 21:45, `scheduler/telegram`, session `20260621_185547_b16abd`): Zaibot Qwen 36 설정 변경. 요청 내용: “크론잡중에서 서울대학교 산업인력개발학과 홈페이지 공지사항 업데이트 되면 알려주는거 있지?”; “[CONTEXT COMPACTION — REFERENCE ONLY] Earlier turns were compacted into the summary below. This is a handoff from a pre…”; “[Replying to: "Cronjob Response: obsidian-link-health-weekly (job_id: 198ef89c3288) ------------- ⚠️ Obsidian 링크 건강검진 완…”
- [[Hermes/Hermes]] 챗봇 후속 작업 감지(2026-06-21 22:40, `zai/telegram`, session `20260621_172834_16471c`): 텔레그램 게이트웨이 상태 확인 #19. 요청 내용: “⏱️ The model provider is rate-limiting requests. Please wait a moment and try again. 응답해 Chatgpt로 전환해 응답해 [Note: model…”; “[CONTEXT COMPACTION — REFERENCE ONLY] Earlier turns were compacted into the summary below. This is a handoff from a pre…”; “You just executed tool calls but returned an empty response. Please process the tool results above and continue with th…”; “[Replying to: "📖 read_file: "/Users/01chungee10/.hermes/profiles/r..." 🔧 patch: "/Users/01chungee10/.hermes/profiles/r.…”
- [[Hermes/Hermes]] 챗봇 후속 작업 감지(2026-06-22 00:32, `work/telegram`, session `20260621_153410_fe5c0e`): Regime Switch Diagnostic Results #8. 요청 내용: "다음 작엄 진행 [CONTEXT COMPACTION — REFERENCE ONLY] Earlier turns were compacted into the summary below. This is a handoff f…"; "[CONTEXT COMPACTION — REFERENCE ONLY] Earlier turns were compacted into the summary below. This is a handoff f…"; "0.4%부터 0.1%까지 0.1 단위로 모두 백테스트해보자 최적의 구간과 앙상블, 알고리즘 탐색"; "과적합 확인"
- [[Hyundai Steel Newtalk]] / [[자유톡톡]] 일상글 주제 랜덤화 개선. `/Users/01chungee10/.hermes/profiles/learn/scripts/newtalk_daily_post.py`의 `make_daily_post()`를 날짜 seed 기반 결정 선택에서 `random.choice()` 진짜 랜덤 선택으로 변경. 주제 풀을 7개에서 28개로 확장(출근길 음악, 업무 중 깜빡, 창밖 풍경, 동료와 대화, 작은 성취 등 추가). 본문 미들 문구 4종, 마무리 문구 4종도 각각 랜덤 선택. 검증: `py_compile` 통과, `--dry-run` 3회 실행 시 매번 다른 주제·본문 조합 생성 확인.
- [[Hyundai Steel Newtalk]] / [[자유톡톡]] 일상글 조합 문구 확장. `/Users/01chungee10/.hermes/profiles/learn/scripts/newtalk_daily_post.py`의 `make_daily_post()`에서 본문 미들 문구를 4종에서 20종으로, 마무리 문구를 4종에서 20종으로 확장. 총 조합 후보는 주제 28 × 미들 20 × 마무리 20 = 11,200가지. 검증: `python3 -m py_compile` 통과, AST 기준 `middles=20`, `closers=20`, `--dry-run` 10회에서 제목 10종·미들 8종·마무리 9종 확인.
- [[Hermes/Hermes]] / [[Telegram]] 챗봇 무응답 재발 대응: 9개 프로필(`research`, `learn`, `memo`, `work`, `family`, `img`, `try`, `zai`, `scheduler`) 대상 숨김형 watchdog 구성. `/Users/01chungee10/.hermes/profiles/research/scripts/telegram_gateway_watchdog.sh` 작성, `/Users/01chungee10/Library/LaunchAgents/ai.hermes.telegram-watchdog.plist`로 120초 주기 실행 등록. 정상 시 stdout/stderr 0바이트, 내부 로그만 `/Users/01chungee10/.hermes/profiles/research/logs/telegram-watchdog.log`에 기록. `gateway_restart_notification: false`를 각 프로필 `telegram:` 설정에 추가하고 Hermes cron 기반 job은 제거하여 사용자 채팅에 watchdog 메시지가 보이지 않도록 조정. 검증: plist lint OK, LaunchAgent loaded, 9개 gateway PID 실행 및 Telegram 연결 로그 확인(2026-06-22 11:16 KST).
- [[TOSS]] / [[Toss Securities Open API]] 문법 및 [[ttak]] loop 검증 기록. 상세: [[Hermes/wiki/references/toss-api-ttak-loop-2026-06-22]]. 공식 랜딩 기준 주문 예시는 `{symbol, side, orderType, quantity, price}`이며 본문은 `POST /api/v1/orders`, 코드 예시는 `https://openapi.tossinvest.com/v1/orders`로 prefix 표기가 엇갈림. 레포 loop 안전 실행 결과: `NO_TRADE`, `LIVE_BLOCKED`, `live_order_submitted=false`; 테스트 `39 passed in 0.34s`.

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
