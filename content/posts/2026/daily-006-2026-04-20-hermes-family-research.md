---
title: "2026-04-20; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-04-20
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - 가족-일상
  - 데이터분석
  - HRD-리더십
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-04-20.md"
---

# 2026-04-20; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-04-20|2026-04-20 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-04-20에는 ACC 어린이문화원 교육신청 준비, WoS 내보내기 결과 점검 (08:26~10:35), WoS 작업 현황 저장 (10:40~10:46), WoS 파이프라인 정리 (16:00경)를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### ACC 어린이문화원 교육신청 준비

- Cron 작업 실행됨 (원래 4/21 10시인데 하루 일찍 실행됨)
- 프로그램: '온몸으로 굽는 레뾰쉬카', '방긋방긋 블루밍 부케'
- 로그인 성공 (brienz311@gmail.com)
- 상세페이지 URL:
  - 온몸으로 굽는 레뾰쉬카: /main/product/detail/346
  - 방긋방긋 블루밍 부케: /main/product/detail/347
- 신청 버튼: `#modal_open_btn` (모달 팝업 열기)
- 현재 상태: "4월 21일(화) 오전 10시 신청 시작"

### WoS 내보내기 결과 점검 (08:26~10:35)

- 사용자가 끊긴 작업 재개 요청.
- `wos_full_*.bib` 점검 결과, **44개 청크가 정상 완료**, 총 **21,987건** 확보 확인.
- 전체 목표 22,487건 중 **누락 청크는 13001~13500 한 개(500건)**만 남음.
- 따라서 WoS Full Record and Cited References 수집은 **97.8% 완료** 상태.
- 기존 `wos_papers.csv`는 과거 2,250건 버전이라 최신 상태를 반영하지 않음. 최신 기준은 bib 청크 합산 수치(21,987건)로 봐야 함.
- 이전 디버그 산출물 정리: `menu_debug*.png`, `modal_error.png`, `modal_full_scan.png`, 테스트용 `wos_chunk_1_500.bib`, `wos_test_1_1000.bib` 삭제.

### 추가 교훈

### WoS 작업 현황 저장 (10:40~10:46)

- 사용자가 나중에 이어서 할 수 있도록 WoS 상태를 기억해둘 것을 요청함.
- 단일 누락 청크였던 `13001~13500`을 재시도했고, regex 기준 501처럼 보였지만 `bibtexparser` 기준으로는 **정상 500건**으로 확인.
- 따라서 `wos_full_*.bib` 기준으로는 **전 청크 확보 완료** 상태로 판단됨.
- 목표 건수: 22,487건.
- 후속 작업은 "수집"이 아니라 **최종 정산/정리 단계**임:
  1. `wos_full_*.bib` 전체를 다시 파싱해 최신 `wos_papers.csv` 재생성
  2. RISS 1,817건과 WoS 최신본을 합쳐 통합 CSV 생성
  3. 필요 시 중복 제거 및 메타연구용 스크리닝 컬럼 추가

### WoS 파이프라인 정리 (16:00경)

- 원칙 확정: **WoS 파이프라인은 bib 확보가 먼저, CSV는 bib에서 재생성되는 파생 산출물**.
- Streamlit WoS adapter도 bib-first로 수정함. `wos_full_*.bib`가 있으면 이를 우선 파싱해 `wos_papers_latest.csv`를 만든 뒤 리뷰용 6컬럼 CSV를 생성하도록 반영.
- 정식 스크립트 추가: `pipeline/collectors/wos_bib_to_csv.py`
- 완료된 WoS bib는 CSV 생성 후 정리 가능하다는 사용자 결정 반영.
- 실제로 `Downloads/meta_study/wos_query_1/`의 `wos_full_*.bib` 45개를 latest CSV 생성 후 정리했고, 현재 남은 원본 탐색 파일은 `wos_papers_latest.csv` (약 47MB, 22,478행)임.

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
