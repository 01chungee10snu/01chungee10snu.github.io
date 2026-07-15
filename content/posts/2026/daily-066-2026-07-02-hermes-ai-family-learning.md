---
title: "2026-07-02; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-07-02
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - AI-LLM
  - 가족-일상
  - HRD-리더십
  - 데이터분석
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-07-02.md"
---

# 2026-07-02; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-07-02|2026-07-02 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-07-02에는 작업 기록를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 작업 기록

- [[Hermes/Hermes]] [[HR After AI]] 상세 메일 정리본 재작성(2026-07-02 00:17 KST): 기존 발송 메일이 전체 내용을 충분히 반영하지 못한다는 사용자 피드백에 따라, 공식 시간표 흐름과 연사별 키워드·토픽 전개 중심의 상세 정리본을 `/Users/01chungee10/Github/Edaily_HR After AI/HR_After_AI_2026_연사별_토픽중심_상세메일.md`로 새로 작성했다. 구성: Reception/Opening, 김판성(TOSS), 임정환(모티프테크놀로지스), 정진우(ACG), 한충석(현대제철), 오일구(EY), Track A 대담, 김덕호(Special), 정정선(IBM), 이덕현(포스코), 염우선(SK하이닉스), Track B 대담, Closing, 실행 과제, 전체 결론. 검증: 457 lines, 21,583 chars, 주요 연사·핵심 토픽 키워드 누락 없음(PASS). HTML 자동 변환은 실행 승인 대기 타임아웃으로 진행하지 않았다.
- [[Hermes/wiki/projects/AutoSNUAPI]] [[SNU 문헌 파이프라인]] 다운로드 경우의 수 battery 구현(2026-07-02 00:40 KST): `tests/test_snu_primo_download_battery.py`를 추가해 auth block, direct/local PDF, iframe/data-url detail recovery, browser-flow CDP missing, document-delivery-only, utility-control no-fulltext, fixture provider 상태 matrix, OA success/invalid PDF, provider profile candidate matrix, resume-skip을 검증했다. `scripts/run_snu_primo_download_battery.py`도 추가해 `--mode quick|targeted|full` offline battery와 `--live-canary --confirm-live` gated canary를 제공한다. 검증: script targeted `22 passed + 15 subtests`, script full 및 직접 pytest `81 passed + 15 subtests`, `py_compile`, `git diff --check`, secret-pattern scan PASS. CDP `9222`/`9223`은 down이라 실제 live canary는 미실행.
- [[Hermes/Hermes]] [[HR After AI]] [[Gog]] 상세 정리본 재발송(2026-07-02 05:07 KST): `/Users/01chungee10/Github/Edaily_HR After AI/HR_After_AI_2026_연사별_토픽중심_상세메일.md`를 Gmail 호환 HTML(`/Users/01chungee10/Github/Edaily_HR After AI/HR_After_AI_2026_연사별_토픽중심_상세메일.html`)로 변환한 뒤 Gog Gmail로 `brienz311@gmail.com`에서 `brienz311@hyundai-steel.com`에 재발송했다. 제목: `[HR after AI 2026] 연사별 키워드·토픽 중심 상세 정리`. Gmail messageId/threadId: `19f1f4ada3d5e1d1`. Sent 라벨 검색으로 발송 확인.
- [[Hermes/Hermes]] [[Cron]] 로컬 cron 오류 원인 탐색(2026-07-02 06:38 KST): `local-cron-error-triage` job `87840873f98d`가 보고한 5건을 확인했다. `hyundai-steel-daily-newsletter`는 DNS가 아니라 Gog 인증 preflight 실패가 실제 원인이며 뉴스 수집·품질검사는 통과했다. 13:00 오후 브리핑은 과거 scheduler/fallback이 미설치 모델 `qwen3.6:27b`를 참조해 실패했으나 현재 `jobs.json`은 `zai/glm-5.2`, config/Ollama는 `qwen3-coder:30b`로 정리되어 있다. `local-session-intent-digest`와 `local-daily-decision-log-extractor`는 cron 실행 제한시간 대비 로컬 LLM 응답 시간이 길어 timeout이 났고, 직접 실행 시 각각 96초/31초로 성공했다. `local-hyundai-news-relevance-filter`는 작업은 성공했으나 Telegram 전달 단계에서 일시적 DNS 연결 오류가 났다. 현재 Google News/Telegram/Google DNS·HTTP probe는 정상.
- [[Hermes/Hermes]] 신규 챗봇 작업 감지(2026-07-01 22:37, `research/telegram`, session `20260701_223649_1ca5dca4`): 한국어 인사 시작. 요청 내용: “[Replying to: "루프 1회 완료했습니다. 실행 결과 CDP 확인 • 상태: 완료 • 결과: 9222는 down, 9223은 Chrome CDP up 첫 live probe • 상태: 완료 • 결과: .e…”; “[Replying to: "loop5를 이어서 진행합니다. 이미 확인된 범위상 실행 계약은 session-probe의 auth → search → detail_probe → resolve_primo_fulltext…”
- [[Hermes/Hermes]] 신규 챗봇 작업 감지(2026-07-01 22:37, `research/telegram`, session `20260701_224009_779dca`): 한국어 인사 시작 #2. 요청 내용: “[Replying to: "루프 1회 완료했습니다. 실행 결과 CDP 확인 • 상태: 완료 • 결과: 9222는 down, 9223은 Chrome CDP up 첫 live probe • 상태: 완료 • 결과: .e…”; “[Your active task list was preserved across context compression] - [>] loop5. PRIMO_DETAIL_FULLTEXT_NOT_FOUND 원인 좁히기: d…”
- [[Hermes/Hermes]] 챗봇 후속 작업 감지(2026-07-01 22:41, `try/telegram`, session `20260701_160340_e57edb`): 텔레그램 챗봇 모델과 Codex 계정 조사 #6. 요청 내용: “터미널을 통해서 antigravity cli를 기반으로 출력을 받아낼 수 있겠어?”; “온라인에서 설치방법 찾아봐”; “Cli 명령어를 통해서 터미널에서 바로 결과값을 받아낼 수 있는지 점검해보세요 Codex cli exec처럼 유사한게 가능한지 여부를 따져봐요”
- [[Hermes/Hermes]] 신규 챗봇 작업 감지(2026-07-01 22:41, `research/telegram`, session `20260701_224103_977f11`): 한국어 인사 시작 #3. 요청 내용: “[Your active task list was preserved across context compression] - [>] loop5. PRIMO_DETAIL_FULLTEXT_NOT_FOUND 원인 좁히기: d…”; “[Your active task list was preserved across context compression] - [>] loop5. PRIMO_DETAIL_FULLTEXT_NOT_FOUND 원인 좁히기: d…”

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
