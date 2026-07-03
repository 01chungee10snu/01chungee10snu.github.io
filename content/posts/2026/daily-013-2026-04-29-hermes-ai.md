---
title: "2026-04-29; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-04-29
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - AI-LLM
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-04-29.md"
---

# 2026-04-29; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-04-29|2026-04-29 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-04-29에는 2026-04-29 00:52 KST — Harness RISS→DBpia direct-provider stage, autoclawsnu PDF 다운로드 개선 작업 기록 - 2026-04-29를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 2026-04-29 00:52 KST — Harness RISS→DBpia direct-provider stage

- Continued PDF acquisition improvement in `C:\Github\harness\Legacy` after user asked to proceed.
- Added `AUTOCLAW_RECORDS_CSV` support to `engines/download_snapshot_based.py`, loading enriched unresolved record metadata by title.
- Added Primo-before direct stage: if a record has `riss_provider_name` containing DBpia and `riss_is_free=1`/`무료`, engine attempts DBpia direct search (`https://www.dbpia.co.kr/search/topSearch?searchOption=all&query=...`) before `process_single_paper` Primo flow. It searches/clicks likely DBpia result links, then reuses existing provider download flow; if it fails, it falls back to Primo.
- Updated `pipeline/runners/download_snapshot_runner.py` to write `unresolved_records_enriched.csv` and pass it to the engine via `AUTOCLAW_RECORDS_CSV`.
- Verified syntax with `python3 -m py_compile` for `pipeline/open_access.py`, `pipeline/runners/download_snapshot_runner.py`, and `engines/download_snapshot_based.py`. Also unit-checked metadata loading and DBpia free-record detection.
- WoS Starter API key retrieved from Clarivate Developer Portal app `wos-starter-test`; stored in Windows User env `WOS_API_KEY` and WSL shell env (`~/.bashrc`, `~/.profile`, `~/.bash_profile`). Did not store the secret value in notes.

### autoclawsnu PDF 다운로드 개선 작업 기록 - 2026-04-29

### 현재 목표
- PDF 원문 수집에서 가장 비용이 큰 Primo/SNU 인증 경로는 최종 fallback으로만 사용한다.
- Primo 전에 WoS/DOI/OA/RISS 무료 제공처 등 cheap/free 경로를 최대한 먼저 시도한다.
- harness, runner, batch/log 계약은 깨뜨리지 않는다.

### 지금까지 정리한 핵심 설계
1. 접근 전략은 provider 이름 기준이 아니라 access 권한 기준이어야 한다.
   - `oa_direct`: OA PDF/저장소/DOI 기반 공개 원문

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
