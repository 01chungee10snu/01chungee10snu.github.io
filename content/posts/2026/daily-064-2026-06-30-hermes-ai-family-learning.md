---
title: "2026-06-30; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-06-30
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - AI-LLM
  - 가족-일상
  - HRD-리더십
  - 업무자동화
  - 데이터분석
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-06-30.md"
---

# 2026-06-30; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-06-30|2026-06-30 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-06-30에는 Quartz 자동 발행 로그, 작업 기록, Quartz 블로그 발행 로그 - ChatGPT 주간 회고 102, Quartz 블로그 발행 로그 - ChatGPT 주간 회고 103를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### Quartz 자동 발행 로그

- [[ChatGPT 대화이력 주간 회고]] 147 발행 완료: [[147_2026년 5월 4주차; 나는 무료 코딩에이전트와 HR After AI 발표, OpenClaw 장비구상과 논리학 번역을 함께 다듬었다]]
- 처리 주간: 2026-05-18~2026-05-24, 건너뛴 빈 주간: 없음
- 핵심 연결: [[무료 코딩에이전트]], [[OpenClaw]], [[PowerShell]], [[OneDrive]], [[HR After AI]], [[제조업 HR]], [[PPTX]], [[수학 학습]], [[Mac]], [[LLM]], [[논리학]], [[궤변]]
- 검증: `npx quartz build` 성공, GitHub Actions run `28424623482` completed success, 라이브 홈페이지 및 `.html` 글 URL 제목/본문 키워드 확인 완료
- 커밋: `efb97c0` (`Add ChatGPT weekly retrospective post 147`)
- 라이브 URL: https://01chungee10snu.github.io/posts/2026/147-2026-05-18-2026-05-24-coding-agent-hr-after-ai-openclaw-onedrive-logic.html

- [[ChatGPT 대화이력 주간 회고]] 146 발행 완료: [[146_2026년 5월 3주차; 나는 이미지 프롬프트와 CL 설문 시각화, Codex 네트워크와 RD·OD 역량체계를 함께 다듬었다]]

### 작업 기록

- 05:26 [[Gog]] [[Google Workspace]] [[OAuth]] 콜백 처리 요청 확인.
- 로컬 `127.0.0.1:64618` 리스너가 없어 기존 콜백을 직접 전달할 수 없었고, Gog 원격 OAuth step 2는 `manual auth state missing`으로 실패함.
- 새 [[Gog]] 원격 OAuth step 1을 생성하여 재인증 URL을 발급함. 인증 완료 후 새 콜백 URL을 다시 받아 step 2로 교환 예정.
- 05:30 새 콜백 URL로 [[Gog]] OAuth step 2 교환 성공: `brienz311@gmail.com`, services `appscript, calendar, contacts, drive, gmail` 저장됨.
- 검증: `gog auth list`에서 대상 계정 scopes 확인, `gog gmail search`, `gog calendar events list`, `gog drive ls`, `gog contacts list`가 대상 계정으로 성공함.

- [[ChatGPT 대화이력 주간 회고]] 098 발행 완료: [[098_2025년 6월 3주차; 나는 사무생산성 혁신과 AI 직업대체 연구, OneDrive 백업과 가족 수학 설명을 함께 다듬었다]]
- 처리 주간: 2025-06-09~2025-06-15, 건너뛴 빈 주간: 없음

### Quartz 블로그 발행 로그 - ChatGPT 주간 회고 102

- 처리 주간: [[2025-07-07]]~[[2025-07-13]]; 건너뛴 빈 주간 없음.
- 새 글: [[102_2025년 7월 2주차; 나는 GPU 학습오류와 LLM 문서정제, PPT 자동화와 MCP 서지관리·프로필 페이지를 함께 다듬었다]]
- 핵심 연결: [[GPU 학습]], [[PyTorch Lightning]], [[LLM]], [[RAG]], [[문서 정제]], [[PowerPoint]], [[MCP]], [[서지관리]], [[GitHub Pages]], [[프로필 웹페이지]]
- 로컬 검증: `npx quartz build` 성공(104 Markdown, 714 files emitted).
- 배포: commit `b2f44153f938b4c5c8d891c1b50ca8f7696e3153`, GitHub Actions run `28403103971` 성공.
- 라이브 검증: 홈페이지와 글 URL에서 새 제목 확인, 본문 키워드 `GPU 학습`, `MCP`, `문서정제`, `프로필 웹페이지` 확인.

### Quartz 블로그 발행 로그 - ChatGPT 주간 회고 103

- 처리 주간: [[2025-07-14]]~[[2025-07-20]]; 건너뛴 빈 주간 없음.
- 새 글: [[103_2025년 7월 3주차; 나는 SAP 자동화와 PPTX 데이터추출, GPU 최적화와 타임라인·가족 판단을 함께 다듬었다]]
- 핵심 연결: [[SAP 자동화]], [[T-Code]], [[SQL]], [[PPTX 자동화]], [[GPU 학습]], [[LM Studio]], [[MCP]], [[GitHub Pages]], [[타임라인 시각화]], [[가족 생활]]
- 로컬 검증: `npx quartz build` 성공(105 Markdown, 720 files emitted).
- 배포: commit `3edae0a`, GitHub Actions run `28403589303` 성공.
- 라이브 검증: 홈페이지와 `.html` 글 URL에서 새 제목 확인, 본문 키워드 `SAP 자동화`, `PPTX 자동화`, `GPU 학습`, `타임라인 시각화` 확인.

- [[ChatGPT 대화이력 주간 회고]] 104 발행 완료: [[104_2025년 7월 4주차; 나는 Claude 접속문제와 WSL 저장공간, Excel 집계와 비트코인·머신러닝 학습을 함께 다듬었다]]

### Quartz ChatGPT 주간 회고 발행 - 2025-09-08~2025-09-14

- [[ChatGPT 대화이력 주간 회고]] 111편을 발행함: [[111_2025년 9월 2주차; 나는 철강 DX 조직개발과 직업교육 정책, 생성형 AI 학습체계와 RAG·JD-R 연구를 함께 다듬었다]]
- 처리 주간: [[2025-09-08]]~[[2025-09-14]]; 건너뛴 빈 주간: 없음
- 핵심 주제: [[철강산업]] [[Digital Transformation]] [[조직개발]] [[직업교육]] [[생성형 AI]] [[RAG]] [[JD-R 모델]]
- Git commit: `1735e52`; GitHub Actions run: `28408205138`
- 라이브 검증: 홈페이지와 게시글 URL에서 제목 및 본문 키워드 확인 완료

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
