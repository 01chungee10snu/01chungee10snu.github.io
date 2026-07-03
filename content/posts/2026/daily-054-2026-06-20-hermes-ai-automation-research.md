---
title: "2026-06-20; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-06-20
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - AI-LLM
  - 업무자동화
  - 데이터분석
  - HRD-리더십
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-06-20.md"
---

# 2026-06-20; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-06-20|2026-06-20 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-06-20에는 작업 기록를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 작업 기록

- [[Hermes/Hermes]] / [[Obsidian]] / [[Hermes/wiki/reports]]: 추천 크론 10·11·12·14·15 작업 시작 및 등록. 신규 cron: `obsidian-link-health-weekly`(`198ef89c3288`, 일 21:00), `weekly-retrospective-obsidian-sunday-22`(`59d3f038e1a0`, 일 22:00), `memory-skill-candidates-weekly`(`f0037bbf83c6`, 토 10:00), `monthly-obsidian-summary`(`8b6d8dfa5436`, 매월 1일 07:30), `macbook-pro-migration-check-weekly`(`c0401de17fbe`, 일 20:30). 스크립트: `/Users/01chungee10/.hermes/profiles/scheduler/scripts/obsidian_link_health.py`, `/Users/01chungee10/.hermes/profiles/scheduler/scripts/macbook_migration_check.py`. 검증: 두 스크립트 수동 실행 성공 및 보고서 생성, `cronjob list`에서 5개 모두 enabled/scheduled 확인.
- [[Hermes/wiki/projects/TOSS]] / [[Hermes/wiki/references/toss-daily-decision-toss-api-integration-2026-06-20]]: Toss API 결합형 일일 투자판단 엔진 1차 구현. `daily run` CLI, panel 기반 후보 점수화, mock/Toss read-only holdings 리뷰, manual_draft_only 주문 초안 생성 추가. 검증: `PYTHONPATH=src .venv/bin/python -m pytest -q` → 94 passed. 실주문은 계속 `live_order_submitted=False` / `live_trading_disabled`로 차단.
- [[Hermes/wiki/projects/TOSS]] / [[Hermes/wiki/references/toss-slow-veto-paper-plan-integration-2026-06-20]]: API 발급 전 후속으로 slow veto와 daily→paper plan 변환 구현. `--slow-veto-events`, `--paper-plan-out`, `daily_decision_to_paper_plan()` 추가. 검증: `tests/test_daily_decision.py` → 6 passed, 전체 `pytest -q` → 97 passed. block 이벤트 시 `manual_drafts=0`, `paper_plan_orders=0`; 이벤트 없음 시 paper order 생성 확인.
- [[Hermes/wiki/projects/TOSS]] / [[Hermes/wiki/references/toss-slow-events-collector-2026-06-20]]: DART/뉴스/manual export를 `slow_events.json`으로 자동 정규화하는 collector 추가. `daily collect-slow-events --source ... --out ...` CLI, JSON/CSV 입력, 한국어 리스크 키워드 severity 분류 구현. 검증: collector tests → 10 passed, 전체 `pytest -q` → 107 passed. CLI smoke에서 CSV→slow_events 생성 후 daily run 연결 시 `manual_drafts=0`, `paper_plan_orders=0` 차단 확인.
- [[Hermes/wiki/projects/TOSS]] / [[Hermes/wiki/references/toss-daily-paper-loop-wrapper-2026-06-20]]: API-less end-to-end paper loop 구현. `daily paper-loop` CLI와 `run_daily_paper_loop()` 추가: daily decision → paper plan → `run_daily_paper()` → decision/plan/result/report artifacts 저장. 검증: RED `ModuleNotFoundError`, GREEN `tests/test_daily_paper_loop.py` → 3 passed, 관련 30 passed, 전체 `pytest -q` → 110 passed. CLI smoke: CLEAR는 `paper_total_orders=1`, BLOCK은 `paper_total_orders=0`, 모두 `live_order_submitted=False`.
- [[Hermes/wiki/projects/TOSS]] / [[Hermes/wiki/references/toss-paper-loop-google-sheets-append-2026-06-20]]: paper-loop 결과를 Google Sheets operator UI에 append하는 옵션 구현. `run_daily_paper_loop(..., sheet_store=...)`, `daily paper-loop --sheet-id ...`, `sheet_writeback` 메타데이터 추가. 검증: RED `unexpected keyword argument 'sheet_store'`, GREEN focused 4 passed, 관련 19 passed, 전체 `pytest -q` → 111 passed. Fake Google API smoke에서 `runs!A:G`, `fills!A:H`, `positions!A:F` append 호출 확인. 실제 Google Sheet 쓰기는 수행하지 않음.
- [[Hermes/wiki/projects/TOSS]] / [[Hermes/wiki/references/toss-empirical-replay-loop-2026-06-20]]: 실증기반 cumulative replay 루프 구현. 실제 496종목 × 974일 패널(2022-2025)로 daily decision scoring을 인메모리 replay. `ReplayEngine`, `run_replay()`, `daily replay` CLI 추가. 검증: RED `ModuleNotFoundError`, GREEN 4 passed, 전체 `pytest -q` → 115 passed. 실증 결과(step=5): +7.12% 수익, -11.24% MDD, Sharpe 0.70, 135거래, 40% 승률. `live_order_submitted=False`.
- [[Hermes/wiki/projects/TOSS]] / [[Hermes/wiki/references/toss-sweep-optimization-2026-06-20]]: 성과비교 파라미터 sweep 루프 구현. `SweepConfig`, `build_grid_configs()`, `run_sweep()`, `daily sweep` CLI 추가. 60개 config 테스트(12+48). 최적 발견: step=10, sl=10%, tp=15% → Sharpe 2.23, return +20.4%, MDD -8.9%. 핵심 인사이트: 넓은 stop/take가 momentum 전략에 압도적 우수. 전체 `pytest -q` → 119 passed.

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
