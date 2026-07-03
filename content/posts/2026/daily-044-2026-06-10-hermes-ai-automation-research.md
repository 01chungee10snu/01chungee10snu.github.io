---
title: "2026-06-10; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-06-10
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - AI-LLM
  - 업무자동화
  - 데이터분석
  - HRD-리더십
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-06-10.md"
---

# 2026-06-10; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-06-10|2026-06-10 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-06-10에는 작업 기록를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 작업 기록

### AutoSNUAPI 실제 SNU Primo 탐색 기반 원문 버튼 프로파일링
- [[AutoSNUAPI]]에서 웹앱/브라우저 기반 원문 획득 흐름을 REST/CLI 제어면으로 전환하는 작업을 계속 진행했다.
- [[autoclawsnu]] Windows CDP 경로로 실제 [[SNU Library]] 로그인 canary를 수행했다.
- 로그인 실패 원인: `SNU Login 하러 가기` 클릭 후 SSO URL 도달 검증 없이 도서관 메인 DOM에서 패스키 입력란을 찾으려 해서 `fido_id_value_not_set`으로 실패했다.
- 조치: [[autoclawsnu]] `core/auth_handler.py`에 `passni/sso/spLogin.php` fallback과 SSO 도달 검증을 추가했다.
- 재검증 결과: SNU Login + 패스키 인증 + Primo 검색 + 상세 화면 진입 성공.
- 실제 Primo 상세에서 확인한 원문/버튼:
  - `PDF 다운로드` → [[LibKey]] `full-text-file`

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
