---
title: "2026-05-19; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-05-19
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - 데이터분석
  - HRD-리더십
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-05-19.md"
---

# 2026-05-19; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-05-19|2026-05-19 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-05-19에는 [[autoclawsnu]] 코딩 파이프라인 전략, [[CloakBrowser]] 통합를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### [[autoclawsnu]] 코딩 파이프라인 전략

### 2단계 코딩 접근법 (충 결정)
1. **1차 스크리닝** (전체 23,526건)
   - 양적연구 vs 질적연구 분류만 수행
   - 모델: [[gpt-5.5]] reasoning=low (건당 ~7초)
   - 결과: 각 논문을 quantitative / qualitative / mixed / review / theoretical / development / other 로 분류

2. **2차 심층코딩** (양적연구만)
   - 1차에서 quantitative로 분류된 논문에 대해서만 전체 스키마 코딩

### [[CloakBrowser]] 통합

- browser_manager.py에 [[CloakBrowser]] 백엔드 통합 완료
- [[RISS]] 수집 테스트 성공 (캡차/봇차단 없음)
- launch_persistent_context → launch() 변경 (profile lock 충돌 해결)

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
