---
title: "2026-07-06; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-07-06
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
source: "Obsidian/Hermes/daily/2026-07-06.md"
---

# 2026-07-06; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-07-06|2026-07-06 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-07-06에는 작업 기록, 성찰를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 작업 기록

### KIS 보유종목 평가 및 SELL 안전검증 반영
- [[KIS]] 실계좌 read-only 조회로 현재 보유가 [[컴퍼니케이]] `307930` 9주, 매도가능수량 9주, 평균단가 6,000원, 현재가 6,040원임을 확인했다.
- 기존 [[TOSS]] live-submit 경로는 SELL 주문을 `sell_requires_sellable_quantity_check`로 일괄 차단하고 있어, 매도가능수량이 확인된 경우에도 dry-run SELL 검증이 통과하지 못했다.
- `src/toss_alpha/execution/live_submit.py`에 `sellable_quantity_violation()`과 `aggregate_sell_quantity_violation()`을 추가해 SELL 주문은 명시적 `sellable_quantity`/`sellable_qty`/`ord_psbl_qty`/`sellableQuantity`가 주문수량을 커버할 때만 통과하도록 반영했다.
- `NaN`/비정상 sellable 값은 무시하고, 동일 종목 복수 SELL 주문의 합계가 매도가능수량을 초과하면 `aggregate_sell_quantity_shortfall`로 차단하도록 보강했다.
- 검증: `PYTHONPATH=src .venv/bin/python -m pytest tests/test_live_submit.py tests/test_reconcile.py tests/test_kis_readonly_connector.py -q` 결과 `26 passed in 2.26s`.
- 검증: [[컴퍼니케이]] 9주 SELL dry-run은 `LIVE_SUBMIT_DRY_RUN_READY`, broker payload `PDNO=307930`, `ORD_QTY=9`, `ORD_UNPR=6040`, violations 없음으로 확인했다.


### 성찰

- 매도 자동화는 매수보다 더 엄격해야 하며, 보유수량이 아니라 매도가능수량 기준으로 검증해야 한다.
- 후보 단위 검증만으로는 동일 종목 복수 SELL 주문의 과매도 위험을 잡지 못하므로 배치 합산 검증이 필요하다.
- 실시간 [[KIS]] 잔고 snapshot을 SELL 후보 생성 단계에 붙여 `sellable_quantity`를 사람이 넣지 않아도 자동 주입되게 만들었다.
- 아직 “수익을 보장”하는 조건이 아니라, 정해진 손절/익절/후보생성 조건이 맞으면 자동 후보 생성과 guarded submit까지 반복하는 구조다. 실주문은 기존 triple opt-in과 정규장 gate를 계속 통과해야 한다.
- 사용자가 자동 실주문 ON을 지시해 확인했다. `toss-ttak-loop.sh`에는 `KIS_LIVE_TRADING_ENABLED=true`, `TOSS_RISK_LIVE_TRADING_ENABLED=true`, `TOSS_LIVE_SUBMIT_ENABLED=true`, `TOSS_LIVE_SUBMIT_DRY_RUN=false`, confirmation phrase가 이미 설정되어 있으며, 설정 검증 결과 `submit_enabled=True`, `dry_run=False`, `live_ready=True`, `missing=[]`다. 다음 평일 09:01 cron에서 조건 충족 시 guarded real-submit 경로가 열린다.

### 손실회피형 유연 공격 frontier 백테스트
- [[TOSS]] `ReplayEngine`에 포트폴리오 단위 `max_equity_drawdown_stop_pct`와 `risk_cooldown_steps`를 추가했다. 개별 종목 손절만으로 부족할 때 전체 equity drawdown 기준으로 강제 청산하고 일정 step 동안 신규 진입을 막는 장치다.

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
