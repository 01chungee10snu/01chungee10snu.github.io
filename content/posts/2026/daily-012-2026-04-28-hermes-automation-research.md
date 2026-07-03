---
title: "2026-04-28; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-04-28
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - 업무자동화
  - 데이터분석
  - HRD-리더십
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-04-28.md"
---

# 2026-04-28; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-04-28|2026-04-28 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-04-28에는 수행 내용, 기억, 교훈, 현재 상태를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 수행 내용

- `autoclawsnu`의 최근 WoS/RISS 개선사항을 `C:\Github\harness\Legacy`에 Harness 스타일로 선택 통합함.
- 통합 반영 파일:
  - `Legacy/config/settings.py`
  - `Legacy/core/browser_manager.py`
  - `Legacy/engines/collect_wos.py`
  - `Legacy/engines/collect_riss.py`
  - `Legacy/pipeline/collectors/wos_collect.py`
  - `Legacy/pipeline/collectors/riss_collect.py`

### 기억

- 사용자는 지금 핵심적으로 확인하려는 것이 **OpenClaw 내장 browser user profile 상태**가 아니라, **윈도우 브릿지를 통한 연구 자동화 경로의 실제 동작**임.
- 연구 자동화 검증의 본선 경로는 다음과 같음:
  - Windows PowerShell
  - Windows Python
  - OpenClawBridge
  - Windows Chrome/CDP
  - Harness/autoclawsnu collector 실행
- `browser profile=user` 관련 경고는 부차적 참고사항일 뿐, 연구 자동화 검증의 1순위 진단 대상은 아님.

### 교훈

1. **연구 자동화 테스트와 OpenClaw browser 프로필 점검을 혼동하지 말 것**
   - `browser profile=user` attach 실패는 OpenClaw 내장 브라우저 툴 경로의 문제다.
   - Windows bridge + Windows Chrome/CDP로 도는 collector 검증과는 동일 문제가 아니다.
   - 본 요청이 연구 자동화 검증이면 우선순위를 브릿지/Windows/CDP/collector에 둬야 한다.
2. **하네스 표준 진입점 문제와 collector 성공을 분리해서 기록할 것**
   - wrapper 성공 = collector 통합은 대체로 성공
   - top-level orchestration 정지 = 하네스 호출 경로의 별도 문제
3. **Telegram 봇 무응답은 봇 자체 사망보다 네트워크 fallback/수신 폴링 상태를 먼저 의심할 것**

### 현재 상태

- Harness 통합: 1차 완료
- Harness WoS wrapper: live success
- Harness 표준 collect entrypoint:
  - RISS success
  - WoS orchestration pending fix
- Telegram Brain bot:
  - 발신 성공
  - 세션 재생성 확인

### 2026-04-28 21:13 KST — Harness PDF acquisition improvement plan

- User explicitly decided the PDF downloader should prioritize always-free/lightweight/fast routes before institutional Primo. Primo should be a late fallback, not the first browser-heavy route.
- Target order: (0) existing download/log dedupe, (1) CSV direct URLs/DOI/source URLs including RISS `url` and WoS DOI/OA fields, (2) Unpaywall DOI lookup, (3) OpenAlex DOI/title OA locations, (4) Semantic Scholar openAccessPdf, (5) Europe PMC/PMC/arXiv/DOAJ-like specialty routes, (6) lightweight landing-page HTML sniffing for `citation_pdf_url`, PDF links and common PDF patterns, (7) direct provider browser access when a concrete landing/provider URL exists, (8) SNU Primo/uresolver/proxy fallback, (9) final page.pdf snapshot only as evidence/review artifact.
- Implementation preference: improve Harness style under `C:\Github\harness\Legacy`, mainly `pipeline/open_access.py` and runner flow before touching engines. Keep Streamlit workflow practical for direct use.
- Implemented first pass in `C:\Github\harness\Legacy\pipeline\open_access.py`: added Unpaywall DOI lookup/candidates, expanded source URL handling beyond `source_url`, added lightweight HTML landing-page PDF sniffing (`citation_pdf_url`, direct PDF/download links, common DOI `/pdf` patterns), and added DOI landing-page sniffing only after normal OA candidates fail to avoid slowing every DOI.
- Verified with `python3 -m py_compile pipeline/open_access.py`; smoke test downloaded `Array programming with NumPy` via `Strategy0_OA_Unpaywall` and HTML extraction helper resolved sample PDF links.
- Ran OA prefetch sample check on first 5 WOS and first 5 RISS final CSV rows. Initial lightweight sniff was too aggressive and treated generic `doi.org`/RISS HTML/download navigation as PDF candidates. Tightened rules: no arbitrary `/pdf` guesses for landing pages; accept explicit `.pdf`, `/pdf`, and `citation_pdf_url` only, plus conservative known scholarly rewrites. Re-ran sample: RISS now cleanly reports no OA candidate instead of false candidate failures; WOS sample still has several genuine 403/HTML unresolved cases. Next useful improvement is a separate RISS/provider-discovery light stage that extracts provider/free labels from RISS detail pages (e.g., DBpia 무료), but does not pretend the RISS page itself is a PDF.
- Added RISS lightweight provider discovery in `pipeline/open_access.py`: for unresolved RISS records, fetches RISS detail HTML, extracts fulltext provider blocks with `fulltext_btn`, captures provider name/url, access label, whether it is free, and canonical RISS detail URL. Sample first 5 RISS rows all discovered `DBpia` with `무료` while still not treating the RISS page itself as a PDF candidate.
- Added `unresolved_records_enriched.csv` output in `pipeline/runners/download_snapshot_runner.py` per batch raw folder so OA-unresolved records can carry RISS provider/free discovery metadata into the next direct-provider stage before Primo.

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
