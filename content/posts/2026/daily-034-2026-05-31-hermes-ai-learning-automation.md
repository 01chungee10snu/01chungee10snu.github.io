---
title: "2026-05-31; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-05-31
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
source: "Obsidian/Hermes/daily/2026-05-31.md"
---

# 2026-05-31; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-05-31|2026-05-31 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-05-31에는 작업 기록를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 작업 기록

- 00:00 자동 기억 정리에서 전날 밤 [[autoclawsnu]] 연구 문제의식 확장을 반영했다. [[생성형 AI 리터러시]]는 인간의 인지적 자동화 협업역량, 로보틱스/협동로봇 수용성은 심동적·물리적 자동화 협업역량으로 보고, 두 축을 `human-autonomy collaboration readiness` 또는 미래 일터 적응역량 관점에서 함께 검토하기로 했다. 문헌 스크리닝 범주는 로보틱스·협동로봇 수용성, 인간-로봇 협업 태도, 자동화 불안/직무대체 인식, AI-로보틱스 통합, 직업교육·재교육을 추가한다.

- [[Hermes/wiki/entities/Bebsu]] 세희 기초 연산 25문항을 문장형/스토리형이 아니라 즉시 풀이 가능한 식 형태로 바꿨다. 예: `2 + 3 = ?`, `6 = 2 + ?`, `4 + ? = 10`. `tests/test_sehee_learning_harness.py`에 한글/스토리 표지어가 stem에 들어가지 않는 회귀 테스트를 추가했다. 검증: `python3 -m pytest tests -q` 39 passed, `npm run qa:sehee` PASS, `npm run build` PASS, `npm run qa:harness` PASS.

- 14:39 [[Hermes/wiki/entities/Bebsu]] 세희 출제 범위를 한자리수 덧셈·뺄셈, 수 모으기, 수 가르기, 짝꿍 수만 나오도록 고정했다. `one_digit` 단독 숫자 확인 토픽을 제거하고 25문항을 5개 토픽 × 5문항으로 맞췄으며, 세희 하네스가 허용 토픽 외 항목을 실패 처리하도록 강화했다. 검증: `python3 -m pytest tests -q` 39 passed, `npm run qa:sehee` PASS, `npm run build` PASS, `npm run qa:harness` PASS.

- 17:40 [[Hermes/wiki/entities/Bebsu]] 초1·초2 문제/정답/해설 감사 범위를 G1/G2로 한정하고 `scripts/audit_g1_g2_problem_answers.py` 및 `tests/test_g1_g2_problem_answer_audit.py`를 추가했다. KMA app items 기준 G1 300문항, G2 300문항 모두 stem/answer 누락은 없고 25슬롯이 채워져 있다. 해설 품질 격차는 G1 빈 해설 9·짧은 해설 116·정답 미노출 해설 207, G2 빈 해설 10·짧은 해설 95·정답 미노출 해설 207로 산출했다. `zai-exec`는 현재 프로세스에 `GLM_API_KEY`/`ZAI_API_KEY`/`Z_AI_API_KEY`가 없어 해설 재작성 실행이 막혔다. 검증: `python3 -m pytest tests -q` 40 passed, `verify_kma_grade_ready.py --grade-band G1/G2 --require-public-assets` PASS.


## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
