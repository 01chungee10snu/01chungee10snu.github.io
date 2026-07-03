---
title: "2026-06-11; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-06-11
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - 데이터분석
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-06-11.md"
---

# 2026-06-11; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-06-11|2026-06-11 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-06-11에는 작업 기록를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 작업 기록

### 13:02 KST — [[AutoSNUAPI]] collector가 기존 [[autoclawsnu]] RISS/WoS 프로세스를 재사용하도록 bridge 구현
- 요청 맥락: WoS와 RISS 데이터 확보 과정을 새로 만들지 않고 기존 [[autoclawsnu]] 웹앱/데이터 확보 프로세스를 fork/port해서 사용하기로 함.
- 구현:
  - `/mnt/c/Github/AutoSNUAPI/src/autosnuapi/collectors/autoclaw_bridge.py` 추가.
  - [[autoclawsnu]] 기존 wrapper `pipeline/collectors/wos_collect.py`, `pipeline/collectors/riss_collect.py`를 Windows PowerShell bridge로 호출하는 명령 생성.
  - legacy stdout의 `riss_csv=...`, `wos_output_dir=...` 산출물을 읽어 CSV/BibTeX/JSON에서 provider rows로 정규화.
  - 정규화 rows를 [[AutoSNUAPI]] source registry에 등록하고 필요 시 acquisition queue에 enqueue.
  - CLI `collectors riss run`에 `--tabs`, `--page-size`, `--delay` 옵션 추가.

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
