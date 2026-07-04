---
title: "2026-06-21; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-06-21
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
source: "Obsidian/Hermes/daily/2026-06-21.md"
---

# 2026-06-21; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-06-21|2026-06-21 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-06-21에는 작업 기록를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 작업 기록

- [[TOSS]] frontier 전략의 2026 최신 데이터 확장 검증과 2023 손실 원인 진단을 수행했다. 기존 random500 universe 496종목 전체를 yfinance로 2026-06-19까지 업데이트했고, 확장 패널 `/Users/01chungee10/Github/TOSS/reports/backtests/random500_seed20260607_2022-01-01_2026-latest_ohlcv_panel.csv`을 생성했다. 현재 `hold_until_exit` frontier는 2022~2026 확장 기준 30bps 후 +46.00%, MDD -10.95%, Sharpe 2.1865이며 2026 YTD는 +1.33%로 플러스지만 약하다. 2023 독립 손실은 stop_loss tail damage가 주원인이고, 단순 stop_loss 8% 축소는 전체 수익을 +46.00%→+38.63%로 훼손해 최선 방어가 아님을 확인했다. 결론은 `SALVAGE / NEXT`, not `PROMOTE`. 상세 기록: [[toss-frontier-2026-update-2023-diagnosis-2026-06-21]].
- [[TOSS]] regime switch probe를 수행했다. 2023 방어형 `t65/sl8/mp3`는 30bps 기준 2023 +7.58%로 base의 2023 -4.20%를 개선하지만, 2026 YTD -6.10%로 실패하고 full return도 +32.14%로 base +46.00%보다 낮다. 2026은 `dispersion_ret20_mean 0.1415`, `mean_vol20 0.0372`, defensive entry `avg_entry_volume_surge 15.33`으로 2023보다 고분산/고변동/거래량 폭주 후보 추격 성격이 강했다. 다음 축은 단순 defensive 고정이 아니라 `max_entry_volume_surge`, `max_entry_vol20`, dispersion 기반 soft overlay 테스트다. 상세 기록: [[toss-regime-switch-probe-2026-06-21]].
- [[TOSS]] ML direct-entry frontier를 수행했다. Apple M5 Pro 15코어/48GB 환경을 활용하기 위해 `scikit-learn`, `xgboost`, `lightgbm`, `optuna`, `pyarrow`, Homebrew `libomp`를 설치했고, 452,242 row feature matrix를 생성했다. `scripts/run_ml_direct_frontier.py`는 LightGBM/XGBoost/HistGB/ExtraTrees/RF/Ridge를 expanding walk-forward로 학습하고 ML prediction을 5거래일 entry ranking에 직접 주입한다. 발견 결과: ExtraTrees direct ML은 30bps 기준 +92.51%, MDD -12.90%, Sharpe 1.3339로 headline return은 base +46.00%를 초과했지만 2026 +87.96% 집중 및 2025 -5.27% 때문에 raw max-return 후보에 그친다. LightGBM은 연도별 독립 replay가 모두 플러스(2023 +10.56%, 2024 +10.01%, 2025 +22.77%, 2026 +100.43%)라 robust signal 후보지만 continuous simulator return +21.84%로 path dependency 검증이 필요하다. 판정: `SALVAGE / NEXT`, not `PROMOTE`. 상세 기록: [[toss-ml-direct-entry-frontier-2026-06-21]].
- [[TOSS]] LLM sentiment overlay를 구축했다. `FISA-conclave/klue-roberta-news-sentiment`(KLUE-RoBERTa 110M)을 M5 Pro MPS에서 로컬 구동하고, Google News RSS로 490종목/8,947개 기사 감성을 분석했다. 2026 YTD에서 `sentiment_rerank`는 base +1.33% 대비 +9.42%, Sharpe 0.58→3.34, 승률 35%→55%로 개선했고, `sentiment_penalty_a10`은 +5.20%와 MDD -3.94%로 drawdown을 절반 이하로 줄였다. 판정: `SALVAGE`; 2022~2024 과거 뉴스/공시 확장 검증 필요. 상세 기록: [[toss-llm-sentiment-overlay-2026-06-21]].
- [[TOSS]] sentiment forward tracking cron을 설정했다. 평일 08:20 KST에 `toss_sentiment_forward_report.sh`가 실행되어 canonical base 후보 상위 80개에 대해 최근 7일 Google News RSS를 수집하고 KLUE-RoBERTa 감성 overlay 후보 Top 10을 Telegram으로 보고한다. Cron `c1c0b106efa3`, 다음 실행 `2026-06-22T08:20:00+09:00`. 수동 wrapper smoke는 35.444초로 통과했고, 산출물은 `reports/harness/sentiment_forward/`에 저장된다. live order 없음, research/manual-draft only. 상세 기록: [[toss-sentiment-forward-cron-2026-06-21]].
- [[TOSS]] 최신 개발 상태 기준으로 `scripts/backtest_sentiment_overlay.py`를 재실행해 canonical ReplayEngine + KLUE-RoBERTa sentiment overlay 결과를 재현 검증했다. 검증 전 `tests/test_replay.py tests/test_sweep.py tests/test_verify.py`는 `19 passed in 1.33s`. 백테스트 데이터는 8,947 rows / 490 symbols / 2025-06-21~2026-06-20이고, 2026 YTD에서 `sentiment_rerank`는 base +1.33% 대비 +9.42%(+8.09%p), Sharpe 0.5769→3.3364, 승률 35.00%→55.00%로 개선했다. `sentiment_penalty_a10`은 +5.20%, MDD -10.28%→-3.94%로 방어형 후보. 2025에서는 base +94.93%가 가장 강하고 sentiment는 거의 중립/소폭 열위. 판정: `SALVAGE`, 최근 구간에서는 유효하나 과거 뉴스/공시 확장 검증 전 `PROMOTE` 금지.
- [[TOSS]] 정량 base score와 KLUE-RoBERTa 감정 rank를 결합한 새 `hybrid` overlay 알고리즘을 개발했다. 공식은 `hybrid_score = quant_rank_pct + alpha * sentiment_rank_pct`이며, `final_score`는 원래 정량점수로 유지해 base-quality threshold를 보존한다. TDD로 `test_replay_engine_prediction_overlay_hybrid_combines_quant_and_sentiment_ranks` RED→GREEN을 거쳤고, 회귀 `20 passed in 1.31s`. 30bps 기준 `sentiment_hybrid_a0p5`는 2026 YTD +12.90%, MDD -5.82%, Sharpe 4.2614로 base +1.33% 및 rerank +9.42%를 초과했고, 2025도 +98.09%로 base +94.93%보다 높았다. 10/30/50bps fine-grid에서도 alpha 0.50 주변이 가장 안정적. 판정: `SALVAGE+ / NEXT`, full-history 검증 전 `PROMOTE` 금지. 상세 기록: [[toss-quant-sentiment-hybrid-overlay-2026-06-21]].
- [[Hyundai Steel Newtalk]] / [[자유톡톡]] 매일 09:30 게시 자동화 점검 및 SSL 실패 수정. 기존 Hermes cron `newtalk-daily-post-0930`(`7d8c33402531`)은 `30 9 * * *`, `enabled=true`, `state=scheduled`, `script=newtalk_daily_post_wrapper.sh`, `no_agent=true`로 등록되어 있었고, 다음 실행은 `2026-06-21T09:30:00+09:00`임을 확인했다. 2026-06-20 09:30 실행은 `SSL: CERTIFICATE_VERIFY_FAILED`로 실패했으며, 원인은 `newtalk.hyundai-steel.com`의 불완전한 HTTPS 인증서 체인으로 확인했다. `/Users/01chungee10/.hermes/profiles/learn/scripts/newtalk_daily_post.py`에 Newtalk 전용 `verify_ssl` 옵션과 기본 SSL 검증 우회(`NEWTALK_VERIFY_SSL=0`, 필요 시 `1`로 엄격 검증)를 추가했고, wrapper 주석을 실제 동작에 맞게 정정했다. 검증: `/usr/bin/python3 -m py_compile` 통과, `--dry-run` 통과, 수정된 SSL 경로로 로그인 성공 및 자유톡톡 게시판 HTTP 200 접근 확인. 현재 시간이 6/21 새벽이므로 실게시/강제 cron run은 조기 게시 방지를 위해 수행하지 않음.

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
