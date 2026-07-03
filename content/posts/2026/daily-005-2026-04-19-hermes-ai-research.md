---
title: "2026-04-19; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-04-19
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - AI-LLM
  - 데이터분석
  - HRD-리더십
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-04-19.md"
---

# 2026-04-19; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-04-19|2026-04-19 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-04-19에는 PIN 자동 입력 문제 (10:35~10:45) — 연결, PIN 자동 입력 문제 (10:35~10:45) — 연결, PDF 검증 시스템 구축 (15:35~16:30), 오매치 근원 분석 결과 (16:20~16:30)를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### PIN 자동 입력 문제 (10:35~10:45) — 연결

- Chrome 재시작 후 재로그인 시 PIN 자동 입력 반복 실패
- PINHelper가 HWND를 찾지만 PostMessage 에러 (잘못된 창 핸들) 반복
- 결국 컴퓨터 재시작 필요
- **교훈**: Chrome 재시작 + 재로그인 루프에서 PIN 입력이 연속으로 실패하면 재시작 중단해야 함
- **TODO**: `_restart_browser()`에서 PIN 실패 감지 시 재시도 중단 로직 필요
/home/brienz311/.openclaw/workspace/memory/2026-04-19.md

### PIN 자동 입력 문제 (10:35~10:45) — 연결

- Chrome 재시작 후 재로그인 시 PIN 자동 입력 반복 실패
- PINHelper가 HWND를 찾지만 PostMessage 에러 (잘못된 창 핸들) 반복
- 결국 컴퓨터 재시작 필요
- **교훈**: Chrome 재시작 + 재로그인 루프에서 PIN 입력이 연속으로 실패하면 재시작 중단해야 함
- **TODO**: `_restart_browser()`에서 PIN 실패 감지 시 재시도 중단 로직 필요

### PDF 검증 시스템 구축 (15:35~16:30)

- `core/agent_engine/verifier.py` 생성 — PDF 첫 페이지 텍스트 vs 요청 제목 비교
- 제목 키워드 70% + 저자 힌트 30% 가중치로 매칭 점수 산출
- 스캔 PDF(텍스트 추출 불가)는 unverifiable로 통과시킴
- 50KB 미만 파일은 too_small으로 판정

### 오매치 근원 분석 결과 (16:20~16:30)

- **3개 오매치 논문 모두 Primo는 올바른 논문을 찾음** (score 0.97)
- **진짜 원인**: T&F/SAGE 페이지에서 PDF 링크 추출 시 사이드바/추천 기사 링크를 잡음
  - 예: `doi/full/10.1080/19322909.2024.2395341` 페이지에서 `a:View PDF`가 `epic.org/.../EPIC-Generative-AI-White-Paper.pdf` 선택
  - CSS 선택자가 너무 광범위 — 본문 밖 사이드바 링크까지 포함
- **해결책**: (1) 현재 DOI가 URL에 포함된 링크만 선택, (2) `article`/`main` 영역 내부만 검색
- 아직 수정 전 — 다음 세션에서 작업 예정

### 현재 다운로드 현황 (16:30 기준)

- ✅ 제목-내용 일치: 24개 (확정)
- ❌ 오매치 (다른 문서): 3개 — Algorithmic Literacy, Facilitating GenAI Literacy, Age of Human Comparison
- ❌ SD 봇 감지: 2개 — Telecommunications Policy, CAEAI
- 🟡 스캔/확인불가: 나머지
- 실제 성공률: 24/40 = 60%

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
