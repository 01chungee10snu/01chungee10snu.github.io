---
title: "2026-05-24; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-05-24
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
source: "Obsidian/Hermes/daily/2026-05-24.md"
---

# 2026-05-24; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-05-24|2026-05-24 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-05-24에는 기록를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 기록

- 09:24 KST, 충이 [[autoclawsnu]] WoS CSV 한국어 번역 작업을 계속 진행하라고 요청했고 Spark 모델도 가능하다고 지시했다.
- 기존 `wos_ko_parallel_20260523_152646` run은 `gpt-5.3-codex` 4-worker로 살아 있었지만 밤새 진행량이 낮고 300초 timeout 로그가 있었다.
- `gpt-5.3-codex-spark` 5행 검증을 별도 CSV로 수행해 성공을 확인했다.
- 기존 4개 worker를 정리하고 같은 shard input/output 파일을 대상으로 Spark 4-worker를 재기동했다.
- 09:31 KST 확인 기준 10,481 / 22,828건 완료, 남은 12,347건, `title_ko`/`keywords_ko` 빈 값 오류 0건, Spark worker 4개 생존. shard 4에는 UID 누락/parse 관련 transient retry 로그가 있었지만 worker는 계속 진행 중.
- 10:07 KST 번역 상황 재확인. [[gpt-5.3-codex-spark]] worker는 사용량 한도에 걸려 09:41경 모두 종료됨. Codex 메시지는 14:26 재시도 가능.
- Spark 정지 시점 진행률은 14,041 / 22,828건(61.51%), 남은 8,787건, 빈 번역 컬럼 오류 0건.
- 대기만 하면 멈춘 상태라 같은 shard output 파일에 `gpt-5.3-codex` 4-worker를 `--batch-size 20`으로 재기동했다. 10:12 KST 기준 14,121 / 22,828건, resume worker 4개 생존.

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
