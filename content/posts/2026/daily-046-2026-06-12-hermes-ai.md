---
title: "2026-06-12; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-06-12
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - AI-LLM
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-06-12.md"
---

# 2026-06-12; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-06-12|2026-06-12 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-06-12에는 AutoSNUAPI acquisition continuation, AutoSNUAPI Fable loop — live acquisition opt-in truthfulness, AutoSNUAPI Fable loop — empirical provider downloader handler v1, AutoSNUAPI Fable loop — authenticated HTTP(S) provider downloader v1를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### AutoSNUAPI acquisition continuation

[[AutoSNUAPI]]의 acquisition waterfall 후속 작업을 연쇄적으로 진행했다.

- 구현: retry / unsupported / terminal failed 라우팅 확장
- 구현: acquired item에 deterministic offline mock PDF download artifact 생성
- 구현: item / provider attempt / master ledger / `runs downloads`에 artifact 연결
- 구현: `FixtureProviderHandler` 추가로 ScienceDirect-style access states 실행형 분류
- 독립 검토: retry queue scheduling field drift, mock PDF secret-byte risk, run summary count drift, REST docs gap 발견 후 수정
- 검증: `PYTHONDONTWRITEBYTECODE=1 python -m pytest tests/test_acquisition_orchestrator.py -q` → 6 passed

### AutoSNUAPI Fable loop — live acquisition opt-in truthfulness

15:38 KST 기준 [[AutoSNUAPI]] 중장기 loop plan을 갱신하고 acquisition live-provider truthfulness slice를 TDD로 진행했다.

- 계획: `docs/plans/2026-06-12-fable-5-loop-remaining-work-rubric.md`에 Loop 6A를 추가/완료 표시
- 구현: `autosnuapi acquisition run --include-live` CLI opt-in 추가
- 구현: `POST /api/v1/acquisition/run`의 `include_live=true` API opt-in 추가
- 구현: `LiveProviderHandler` placeholder 추가 — empirical live downloader 미구현 상태에서는 offline mock PDF를 만들지 않고 `LIVE_PROVIDER_HANDLER_UNIMPLEMENTED`로 unsupported route 처리
- 보안: live evidence는 `source=live_opt_in`, `empirical_live=false`로 truthfulness를 보존하고, provider label에 cookie/session/token/password류 문자열이 있으면 `redacted_provider`로 축약
- 검증: RED에서 CLI `--include-live` 미지원/API acquired 오판 실패 확인

### AutoSNUAPI Fable loop — empirical provider downloader handler v1

16:40 KST 기준 [[AutoSNUAPI]] acquisition live opt-in 뒤에 empirical provider downloader handler v1을 추가했다.

- 구현: `LiveProviderHandler`가 `direct_pdf_path`, `pdf_path`, `local_pdf_path`, `download_path`, `direct_pdf_url`, `pdf_url`, `download_url` local/file PDF reference를 인식
- 구현: `--include-live` 상태에서 명시 local/file PDF가 있으면 실제 PDF bytes를 run `downloads/`로 복사하고 artifact/ledger/provider attempt/`runs downloads`에 sha256 연결
- 구현: 성공 evidence는 `source=live_opt_in`, `empirical_live=true`, `download_method=local_file`
- 구현: HTTP/HTTPS remote URL은 아직 fake success하지 않고 `LIVE_PROVIDER_REMOTE_DOWNLOAD_UNIMPLEMENTED` unsupported route
- 구현: missing local file은 `LIVE_PROVIDER_FILE_NOT_FOUND`, non-PDF는 `LIVE_PROVIDER_INVALID_PDF` terminal failure
- 보안: provider/path evidence의 sensitive marker를 `password/passwd/token/cookie/session/authorization/secret/credential/pin`으로 확장하고 secret-like path/provider는 redaction

### AutoSNUAPI Fable loop — authenticated HTTP(S) provider downloader v1

22:49 KST 기준 [[AutoSNUAPI]] acquisition `--include-live` remote downloader slice를 TDD로 진행했다.

- 구현: HTTP(S) `direct_pdf_url`/`pdf_url`/`download_url`은 metadata의 `download_headers` 또는 `auth_headers` dict가 있을 때만 authenticated request로 다운로드
- 구현: 성공 시 실제 provider response PDF bytes를 run `downloads/`로 저장하고 provider attempt/ledger/`runs downloads`에 artifact id와 sha256 연결
- 구현: 성공 evidence는 `source=live_opt_in`, `empirical_live=true`, `download_method=remote_http`, `url_scheme`, `status_code`, `artifact_id`, `sha256`
- 보안: Authorization/header value, raw URL, query token, host는 evidence/CLI payload에 직렬화하지 않음. 테스트 HTTP 서버는 header 수신을 확인하지만 payload에는 token/host가 없어야 함
- 구현: 인증 header 없는 remote URL은 계속 `LIVE_PROVIDER_REMOTE_DOWNLOAD_UNIMPLEMENTED`로 truthful unsupported
- 구현: 401/403은 `LIVE_PROVIDER_AUTH_REQUIRED` manual review, HTTP/network failure는 retryable, oversized는 `LIVE_PROVIDER_REMOTE_FILE_TOO_LARGE`, non-PDF는 `LIVE_PROVIDER_INVALID_PDF`

### AutoSNUAPI Fable loop — authenticated remote downloader verifier hardening

23:19 KST 기준 [[AutoSNUAPI]] HTTP(S) provider downloader v1 verifier 지적사항을 보완했다.

- 1차 verifier: `include_live=true` + auth headers만 있으면 localhost/private/link-local/userinfo target으로 요청 가능한 SSRF 위험을 FAIL로 지적
- 보완: `_remote_target_error()`로 localhost/private/link-local/multicast/reserved/unspecified/missing-host/userinfo target을 기본 `LIVE_PROVIDER_REMOTE_TARGET_BLOCKED` 처리
- 보완: target validation을 header presence check보다 먼저 실행해 header가 없어도 unsafe target은 blocked로 분류
- 보완: `_NoRedirect`로 urllib implicit redirect follow 비활성화
- 보완: auth header key/value CR/LF 및 빈 header name은 `LIVE_PROVIDER_INVALID_AUTH_HEADERS`
- 보완: private/localhost local canary는 `AUTOSNUAPI_ALLOW_PRIVATE_REMOTE_DOWNLOADS=1` env가 있을 때만 허용

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
