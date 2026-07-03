---
title: "2026-06-03; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-06-03
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - 가족-일상
  - HRD-리더십
  - 업무자동화
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-06-03.md"
---

# 2026-06-03; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-06-03|2026-06-03 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-06-03에는 작업 기록를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 작업 기록

- 10:51 [[Ttak]] 질문스킬 고도화 작업을 현재 상태까지 기록했다. `openclaw-imports/ttak/SKILL.md`의 Phase 1이 `Question Gate v2`로 확장된 것을 검증했고, `references/question-gate-v2.md` 신설 및 `references/agent-prompts.md`의 Clarity/Interviewer 프롬프트 확장을 확인했다. 핵심 변경은 질문 전 evidence preflight, Discoverable Fact/Confirmable Interpretation/Human Decision 라우팅, 7개 readiness gate(Objective/User Experience/Core Loop/Asset Role/Non-goals/Success Criteria/Decision Boundaries), “알아서” 기본값 승인 패턴이다. 상세 기록은 [[Hermes/wiki/projects/Ttak-Project-Forge/ttak-skill-improvement]]에 반영했다.
- 15:59 [[autoclawsnu]] 웹앱으로 [[Adaptive Expertise]] 문헌 수집이 가능한지 확인했다. `streamlit_app.py`와 `webapp/main.py` 기준 웹앱에는 `⑤ 리포트·도구`/`0️⃣ 검색어로 논문 수집` 화면과 FastAPI `/sources/collect/wos`, `/sources/collect/riss` 엔드포인트가 있으며, [[RISS]] 수집기는 한글 키워드·국내학술논문/학위논문 탭·page size·delay·CSV 경로를 받는다. [[WoS]]는 keyword/query 방식으로 실행 가능하다. 실제 수집 전략은 [[Hermes/wiki/references/adaptive-expertise-wos-riss-collection-plan-2026-06-02]]의 한글 RISS 검색어 세트를 포함해 진행하기로 정리했다.
- 18:45 사용자 동의 후 [[autoclawsnu]]에서 [[Adaptive Expertise]] 전용 [[WoS]]/[[RISS]] 문헌 리스트를 수집·통합했다. WoS 브라우저 수집은 SNU 패스키 인증 자동화가 실패하여 `WOS_API_KEY` 기반 WoS Starter API로 대체했고, RISS는 headless Chrome RIS export가 일부 쿼리에서 timeout되어 RISS 검색 HTML 직접 파싱 fallback을 병행했다. 최종 산출물은 `/mnt/c/Github/autoclawsnu/runs/adaptive_expertise_integrated_20260603_1845/`에 저장했으며 raw 5,272행, dedup 5,201행, 중복 71행, priority screening 3,681행이다. flag는 adaptive_expertise_core/workplace_hrd_context/human_ai_robot_context/measurement_scale_candidate/review_or_theory_candidate/already_in_generative_ai_corpus로 생성했다.
- 18:49 [[RISS]] headless background process `proc_745ecc7d9ed2` 종료 알림을 확인했다. 프로세스는 exit `-15`로 중단되었고 일부 쿼리는 Playwright `Page.goto` timeout이 있었으나, 최종 deliverable은 이미 더 포괄적인 direct fallback 수집본(`/mnt/c/Github/autoclawsnu/runs/adaptive_expertise_riss_direct_20260603_184344/`)을 입력으로 사용해 [[RISS]] dedup 3,432행을 포함하고 있음을 재검증했다.
- 18:55 [[Adaptive Expertise]] 통합 runs 폴더에서 주제어별·DB별·검색어별 자료 개수를 산출했다. 산출물은 `/mnt/c/Github/autoclawsnu/runs/adaptive_expertise_integrated_20260603_1845/adaptive_expertise_counts_by_topic_db_query.csv`, `.summary.json`, `.md`에 저장했다. 기준은 raw 5,272행 및 dedup 5,201행이며, dedup 기준 [[WoS]] 1,769행·[[RISS]] 3,432행이다.
- 16:37 [[Bebsu]]에 `문제지 풀고 뱁콩받기` 수동 보상 기능을 TDD로 구현했다. 방 화면 버튼/모달, 엄격모드, 추천기본값, 21~25번 고난도 보너스, `reward_ledger` 기록, 부모 화면의 문제지 보상 기록·구간별 정답률·학습지도 가이드를 추가했다. Supabase 최적화는 비파괴 인덱스 migration `202606030001_manual_quiz_reward_dashboard_indexes.sql`을 준비했으며, 현재 환경에는 원격 DB admin credential/Docker daemon이 없어 DB push는 미수행이다. 검증은 신규 테스트 4 passed, 전체 테스트 53 passed/1 skipped, `npm run build` 성공, browser smoke로 모달·부모 화면 섹션 표시 확인. 상세 기록: [[Hermes/wiki/references/bebsu-manual-quiz-reward-2026-06-03]].
- 20:54 [[Hermes_memo Telegram bot]]의 provider 실패 메시지를 진단·수정했다. `memo` 프로필 로그에서 `openai-codex/gpt-5.5`가 긴 Telegram 세션에서 90초 무응답, `Broken pipe`, `max_retries_exhausted`로 실패하는 것을 확인했다. `/home/brienz311/.hermes/profiles/memo/.env`에 `HERMES_CODEX_TTFB_TIMEOUT_SECONDS=0`을 추가하고 `hermes-memo` tmux gateway를 재시작했으며, 과대해진 Telegram DM 세션 매핑(`/home/brienz311/.hermes/profiles/memo/sessions/sessions.json`, last_prompt_tokens 약 42k)을 백업 후 `{}`로 초기화했다. 검증은 `hermes --profile memo chat -q ... --toolsets safe --quiet`에서 `OK`, gateway log에서 `Connected to Telegram` 및 `Gateway running with 1 platform(s)` 확인.
- 21:42 [[Hermes_memo Telegram bot]] 재발방지 노하우를 정리했다. 이번 재발은 `gpt-5.4`로 이미 전환된 상태에서도 Telegram 기존 세션 context가 약 37k tokens까지 커지고 `Non-streaming API call stale for 90s`가 발생한 케이스였으므로, 모델 호환성 문제와 stale-timeout 문제를 분리해서 진단하도록 정리했다. `hermes-telegram-gateway-operations` skill의 `references/provider-timeout-and-session-reset.md`에 `HERMES_API_CALL_STALE_TIMEOUT=600`, `providers.openai-codex.stale_timeout_seconds=600`, 세션 매핑 백업 후 초기화, 짧은 Telegram 테스트 검증 순서를 추가했다. 상세 런북: [[Hermes/wiki/references/hermes-memo-provider-stale-timeout-runbook-2026-06-03]].

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
