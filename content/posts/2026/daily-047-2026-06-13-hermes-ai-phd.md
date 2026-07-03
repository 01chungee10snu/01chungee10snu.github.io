---
title: "2026-06-13; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-06-13
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - AI-LLM
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-06-13.md"
---

# 2026-06-13; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-06-13|2026-06-13 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-06-13에는 연결 — acquisition browser/CDP adapter v1, 연결 — provider별 PDF 다운로드 후보/실행 완성, 연결 — legacy DB provider PDF 후보 포팅, 연결 — provider별 실제 PDF 다운로드 smoke test를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 연결 — acquisition browser/CDP adapter v1

- [[Hermes/Hermes]]
- [[AutoSNUAPI]]
- [[AutoSNUAPI/acquisition]]
- [[AutoSNUAPI/provider-download]]

### 작업 — acquisition browser/CDP adapter v1
- 사용자 선택 "2"에 따라 [[AutoSNUAPI]] acquisition live opt-in의 browser-auth/CDP captured request adapter v1을 구현했다.
- `browser_auth_request` / `cdp_pdf_request` / `cdp_request` metadata의 CDP-style `request.url` + `request.headers`를 기존 authenticated remote downloader에 연결했다.

### 연결 — provider별 PDF 다운로드 후보/실행 완성

- [[Hermes/Hermes]]
- [[AutoSNUAPI]]
- [[AutoSNUAPI/acquisition]]
- [[AutoSNUAPI/provider-download]]
- [[SNU Primo]]

### 작업 — provider별 PDF 다운로드 후보/실행 완성
- [[AutoSNUAPI]] `LiveProviderHandler`에 provider별 PDF 후보 추출/실행 경로를 추가했다.

### 연결 — legacy DB provider PDF 후보 포팅

- [[Hermes/Hermes]]
- [[AutoSNUAPI]]
- [[AutoSNUAPI/acquisition]]
- [[AutoSNUAPI/provider-download]]
- [[autoclawsnu]]
- [[SNU Primo]]

### 작업 — legacy DB provider PDF 후보 포팅

### 연결 — provider별 실제 PDF 다운로드 smoke test

- [[Hermes/Hermes]]
- [[autoclawsnu]]
- [[SNU Primo]]
- [[AutoSNUAPI/provider-download]]
- [[SNU Library]]

### 작업 — provider별 실제 PDF 다운로드 smoke test
- Windows Bridge + Chrome CDP `18811` + SNU 로그인 세션을 사용해 provider별 실제 원문 PDF 다운로드 smoke test를 수행했다.

### 연결 — dCollection/stale-tab provider 후보 하드닝

- [[Hermes/Hermes]]
- [[AutoSNUAPI]]
- [[AutoSNUAPI/acquisition]]
- [[AutoSNUAPI/provider-download]]
- [[SNU Primo]]
- [[SNU dCollection]]
- [[autoclawsnu]]


## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
