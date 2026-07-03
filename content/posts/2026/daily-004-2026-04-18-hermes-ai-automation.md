---
title: "2026-04-18; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-04-18
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - AI-LLM
  - 업무자동화
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-04-18.md"
---

# 2026-04-18; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-04-18|2026-04-18 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-04-18에는 Evening session (21:00-22:35), Evening session (21:00-23:35), 📌 교훈 (Lessons Learned)를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### Evening session (21:00-22:35)

### WoS Collection Pipeline — 완료 — Evening session (21:00-22:35)
- `완성본/collect_wos.py` 디버깅 완료 — SNU proxy → WoS Advanced Search → BibTeX export
- 25 papers collected (18.9KB .bib), CSV 변환: `Downloads/wos_papers.csv`
- WoS CAPTCHA: false positive 수정 (recaptcha/hcaptcha 키워드 필터), 실제 CAPTCHA는 수동 해결 필요
- Anti-detect: `navigator.webdriver` 제거, OneTrust consent layer dismiss 추가

### 해외 논문 다운로드 파이프라인 — Phase 0/0.5 구축 — Evening session (21:00-22:35)
- **3-tier 아키텍처**: Phase 0 (OA 무료) → Phase 0.5 (DOI 웹검색) → Phase 1 (Primo) → Phase 2 (다운로더) → Phase 3 (스냅샷)

### Evening session (21:00-23:35)

### WoS Collection Pipeline — 완료 — Evening session (21:00-23:35)
- `완성본/collect_wos.py` 디버깅 완료 — SNU proxy → WoS Advanced Search → BibTeX export
- 25 papers collected (18.9KB .bib), CSV 변환: `Downloads/wos_papers.csv`
- WoS CAPTCHA: false positive 수정 (recaptcha/hcaptcha 키워드 필터), 실제 CAPTCHA는 수동 해결 필요
- Anti-detect: `navigator.webdriver` 제거, OneTrust consent layer dismiss 추가

### 해외 논문 다운로드 파이프라인 — Phase 0/0.5 구축 — Evening session (21:00-23:35)
- **3-tier 아키텍처**: Phase 0 (OA 무료) → Phase 0.5 (DOI 웹검색) → Phase 1 (Primo) → Phase 2 (다운로더) → Phase 3 (스냅샷)

### 📌 교훈 (Lessons Learned)

### 1. API 먼저, 브라우저는 최후수단
- **Unpaywall/Semantic Scholar API**가 브라우저 자동화보다 100배 빠르고 안정적
- DOI가 있으면 무조건 API 먼저 조회 → 실패 시 브라우저
- `requests` 순수 HTTP는 브라우저 의존성 제거 (Chrome 크래시/PIN/SSO 문제 없음)

### 2. Chrome PDF 뷰어 = 브라우저 킬러
- EBSCO/ProQuest/SD PDF 뷰어 탭이 Chrome을 거의 매번 크래시시킴
- `--disable-pdf`는 유효한 Chrome 플래그가 아님

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
