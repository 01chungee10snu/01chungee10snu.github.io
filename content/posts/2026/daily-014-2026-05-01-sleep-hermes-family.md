---
title: "2026-05-01; 나는 몸의 반응을 관찰하며 생활 리듬을 기록했다"
date: 2026-05-01
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - 자기돌봄
  - 건강기록
  - 가족-일상
  - Hermes
  - 인프라-도구
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-05-01.md"
---

# 2026-05-01; 나는 몸의 반응을 관찰하며 생활 리듬을 기록했다

## 연결

- [[Hermes/daily/2026-05-01|2026-05-01 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-05-01의 기록은 몸의 반응을 관찰하고 생활 리듬과 연결해 해석하려는 시도였다. 복용 이후의 컨디션 변화를 단정하지 않고, 수면량과 일상 리듬이라는 주변 조건까지 함께 보려 했다. 이 날의 의미는 문제를 즉시 결론내리기보다, 반복 관찰이 가능한 형태로 남겼다는 데 있다.

## 기록에서 건진 것

### 구글 캘린더 일정 추가

- 크라운제과 과자체험실 / 2026-06-10 (수) 14:00~15:10 / 예약번호 1223449582 / 인원 2명
- gog CLI로 추가함 (`gog calendar create primary`)

### Obsidian 일기 추가

- `/mnt/c/Obsidian/HCS/충석/일기/2026-04-30.md` 작성
- 내용: 봄이 화, 태희 수학, 진심으로(판교 병원) 예약 — 목요일 오후 6시

### 기억할 것

- **일정 추가 요청 → 항상 gog CLI 사용** (TOOLS.md에 반영 완료)

### autoclawsnu — Document Identity Harness 구축

### 작업 내용
- `core/document_identity.py`: DocumentIdentityResult 구조체 (verified/wrong_document/invalid_pdf/needs_review)
  - DOI 매칭, 제목 토큰 오버랩, page-count 게이트(1페이지 이하 거부)
- `core/pdf_verification.py`: 로그 row에 검증 결과 주입
- `core/primo_match.py`: MatchDecision + accepted 플래그, 출판 수정자 감지(Correction/Erratum/Corrigendum/Retraction/Comment/Reply)
  - `pick_best_match_decision`이 rejected-only 후보군이면 None 반환
- `pipeline/download_backlog.py`: wrong_document/invalid_pdf 분류 경로 추가
- `pipeline/runners/download_snapshot_runner.py`: verification_failed_count에 wrong_document/invalid_pdf 포함

### autoclawsnu — ScienceDirect PDF 다운로드 디버깅

### 원인 분석
- 기존 run에서 ScienceDirect 실패는 **Cloudflare가 HeadlessChrome User-Agent를 차단**
- 로그에 `HeadlessChrome/147` + `CLOUDFLARE_ERROR_1000S_BOX` 확인
- SNU 구독/접근 권한 문제가 아니라 **bot 탐지 문제**

### 시도한 것
1. **CDP User-Agent 오버라이드** (`Network.setUserAgentOverride`) → navigation에는 적용되지만 `request.get()`에는 적용 안 됨
2. **Headed Chrome + OpenClaw 공유 프로필** → ✅ 메인 페이지 정상 로드, View PDF 버튼 발견됨

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
