---
title: "2026-06-07; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-06-07
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
source: "Obsidian/Hermes/daily/2026-06-07.md"
---

# 2026-06-07; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-06-07|2026-06-07 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-06-07에는 작업 기록, 작업 기록 - @Hermes_LearnBOT 오류 복구 및 재발방지를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 작업 기록

### [[Hermes/wiki/projects/TOSS]] 예제 모멘텀 백테스트 실행
- 충의 “백테스트 해봐” 요청에 따라 `/mnt/c/Github/TOSS/goals/example_momentum.yaml` 기준으로 research-only 백테스트를 실행했다.
- 전략: MA20 > MA60이면 다음 거래일부터 long, 아니면 cash. 룩어헤드 방지를 위해 신호는 종가 기준, 포지션은 다음 거래일부터 적용했다.
- 대상/기간: [[삼성전자]] `005930`, [[SK하이닉스]] `000660`; 2022-01-01 ~ 2025-12-31. 데이터는 yfinance adjusted daily close.
- 비용 가정: 수수료 1.5bps/side, 슬리피지 5bps/side, 매도세 18bps on sells.
- 결과 요약: 동일가중 포트폴리오 총수익률 137.18%, CAGR 24.19%, MDD -38.45%, Sharpe 0.965.
- 개별 결과: 삼성전자 총수익률 47.14%, MDD -32.9%; SK하이닉스 총수익률 227.22%, MDD -45.51%.
- 산출물: `/mnt/c/Github/TOSS/reports/backtests/example_momentum_2022-01-01_2025-12-31.md`, `.json`, 각 종목/포트폴리오 curve CSV.

### 작업 기록 - @Hermes_LearnBOT 오류 복구 및 재발방지

### 연결
- [[Hermes]]
- [[Hermes/wiki/entities/hermes-telegram-bots]]
- [[Hermes/wiki/entities/Hermes_LearnBOT]]
- [[Hermes/wiki/references/NotebookLM]]

### 수행
- `hermes-gateway-learn.service` 로그에서 `openai-codex` + `gpt-5.5` 호출이 90초 stale 후 `[Errno 32] Broken pipe`로 반복 실패하는 패턴을 확인했다.

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
