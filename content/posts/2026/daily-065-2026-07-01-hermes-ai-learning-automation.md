---
title: "2026-07-01; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-07-01
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
source: "Obsidian/Hermes/daily/2026-07-01.md"
---

# 2026-07-01; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-07-01|2026-07-01 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-07-01에는 작업 기록를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 작업 기록

- [[Hermes/Hermes]] 챗봇 후속 작업 감지(2026-07-01 02:13, `zai/telegram`, session `20260630_123747_84639e91`): GitHub CLI 인증과 PAT 확인. 요청 내용: “[Replying to: "Pat님, 현재 통계학 학습 게임 프로젝트는 로컬 머신에 존재하며, GitHub Pages로 배포하기 위한 준비가 완료되었습니다. 다음 단계를 차례로 실행하겠습니다: 1. 새로운 GitH…”
- [[Hermes/Hermes]] 신규 챗봇 작업 감지(2026-07-01 05:15, `zai/telegram`, session `20260701_051511_ede98255`): [Replying to: "Pat님, 통계학 학습 게임 프로젝트를 GitHub Pages에 성공적으로 배포했습니다. 다음과 같은 작업이 완료되었습니다: 1. 프…. 요청 내용: “[Replying to: "Pat님, 통계학 학습 게임 프로젝트를 GitHub Pages에 성공적으로 배포했습니다. 다음과 같은 작업이 완료되었습니다: 1. 프로젝트 파일을 GitHub 저장소에 업로드함 2. 저장…”
- [[Hermes/wiki/projects/AutoSNUAPI]] browser agent 첫 slice 후속 검토: 사용자 관점 결함 후보 5개를 `tests/test_browser_agent_contracts.py`에 재현 테스트로 추가하고, `src/autosnuapi/browser_agent/validator.py`·`ledger.py`를 최소 보강했다. 검증: `uv run --extra dev pytest tests/test_browser_agent_contracts.py -q` → 10 passed, `uv run --extra dev pytest -q` → 315 passed + 38 subtests passed.
- [[Hermes/wiki/projects/AutoSNUAPI]] Power Automate 대비 차별화 포인트 확보: `docs/reports/2026-07-01-power-automate-differentiation.md`에 contract-first browser runtime, SNU/학술기관 workflow 특화, evidence ledger, provider-neutral LLM, 보안 gate, CLI/API 제품화 포지셔닝을 정리했다.
- [[Hermes/wiki/projects/AutoSNUAPI]] 사용자 친화 패키징/배포 전략 작성: `docs/reports/2026-07-01-packaging-distribution-strategy.md`에 개인용 로컬 데스크톱 앱 + CLI/API 엔진 + workflow pack 3단 구성, 단계별 배포 채널, doctor/human-gate/run-dashboard UX, MVP ticket을 정리했다.
- [[Hermes/wiki/projects/AutoSNUAPI]] GUI 기반 CDP workflow builder 제품 구체화: `docs/reports/assets/gui-builder-wireframe-v0.png`로 와이어프레임을 만들고, `docs/reports/2026-07-01-gui-builder-product-vision.md` 및 `docs/plans/2026-07-01-gui-cdp-workflow-builder-mvp-plan.md`에 요소 선택 → action 지정 → 정규화 YAML/JSON script → dry-run → CSV/Excel 반복 실행 → run dashboard/ledger 흐름을 정리했다.
- [[Hermes/wiki/projects/AutoSNUAPI]] GUI CDP workflow builder M1 구현: `src/autosnuapi/workflows/`에 workflow 계약·JSON loader·validator·summary 모듈을 추가하고 `autosnuapi workflows validate --workflow-file ... --json` CLI를 연결했다. 신규 focused 테스트 `tests/test_workflow_contracts.py` 작성 후 검증: `uv run python -m pytest tests/test_workflow_contracts.py -q` → 6 passed, `uv run python -m pytest tests/test_workflow_contracts.py tests/test_browser_agent_contracts.py tests/test_api_cli.py -q` → 20 passed, `uv run python -m compileall -q src/autosnuapi tests/test_workflow_contracts.py` → exit 0.
- [[TOSS]] [[forward-tracking]] 2026-01-01 시작 가정 paper portfolio 풀 시뮬레이션을 생성했다. 스크립트: `/Users/01chungee10/Github/TOSS/scripts/simulate_paper_portfolio_from_0101.py`, 산출물: `/Users/01chungee10/Github/TOSS/reports/harness/paper_portfolio/full_sim_2026_from_0101/`. 기간 2026-01-02~2026-06-30 120거래일, 최종 ₩1,263,141(+26.31%), Sharpe 1.19, MDD -20.80%, 주문 514건, 종료거래 253건, 승률 41.1%. 검증: row 수·기간·paper_only/live_order_submitted·포지션 cap·현금 음수 없음·최종 equity 일치 모두 PASS.

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
