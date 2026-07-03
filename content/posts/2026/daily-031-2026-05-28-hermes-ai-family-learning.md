---
title: "2026-05-28; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-05-28
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
source: "Obsidian/Hermes/daily/2026-05-28.md"
---

# 2026-05-28; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-05-28|2026-05-28 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-05-28에는 작업 기록 - Codex 행단위 분류 빠른 모델 전환, 작업 기록 - 태희 체험학습 보고서 보관, 작업 기록 - ChatGPT 가족정보 그룹화, 작업 기록 - 가족 캐릭터 특징 분석를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 작업 기록 - Codex 행단위 분류 빠른 모델 전환

- 연결: [[Hermes/wiki/entities/autoclawsnu]], [[Hermes/wiki/references/Codex]]
- 사유: `gpt-5.3-codex` 행단위 분류가 약 1,075행/시간 수준으로 느려, 빠른 모델 요청에 따라 전환.
- 전환 전 진행: 1,780 / 27,666행, 6.43%.
- 조치: 기존 4개 worker 정지 후 `gpt-5.3-codex-spark`, batch size 40, worker 4개로 재시작.
- 새 background process: `proc_48d7f0d7371f`. 기존 shard output은 유지되어 이어서 진행.

### 작업 기록 - 태희 체험학습 보고서 보관

- 연결: [[태희]], [[충석/가족/태희]], [[2026-05-26 서울우유 양주공장 체험학습 보고서]]
- 요청: 첫째딸 [[태희]]가 작성한 학교장허가 교외체험학습 결과보고서 사진을 기록.
- 조치: 원본 이미지를 Obsidian 가족 기록 assets에 복사하고, 별도 노트에 요약·본문 전사·관찰 메모를 작성.
- 기록 위치: `/mnt/c/Obsidian/HCS/충석/가족/태희/2026-05-26 서울우유 양주공장 체험학습 보고서.md`

### 작업 기록 - ChatGPT 가족정보 그룹화

- 연결: [[충석/가족]], [[충석/가족/보미]], [[충석/가족/태희]], [[충석/가족/세희]], [[충석/가족/ChatGPT 가족정보 그룹]]
- 요청: ChatGPT 대화이력 중 가족 관련 정보를 별도 그루핑. 가족 구성원 이름은 보미, 태희, 세희로 확정.
- 조치: ChatGPT 대화 아카이브에서 `보미/김보미/태희/한태희/세희/한세희` 키워드를 스캔해 117개 관련 대화를 찾고, 사람별·주제별 색인을 생성.
- 생성/갱신 노트: `충석/가족/가족.md`, `충석/가족/보미.md`, `충석/가족/태희.md`, `충석/가족/세희.md`, `충석/가족/ChatGPT 가족정보 그룹.md`.
- 개인 프로필 메모리: 가족 구성원 이름을 보미, 태희, 세희로 저장.

### 작업 기록 - 가족 캐릭터 특징 분석

- 연결: [[충석/가족]], [[충석/가족/가족 캐릭터 특징 분석]], [[충석/충석]], [[충석/가족/보미]], [[충석/가족/태희]], [[충석/가족/세희]]
- 요청: ChatGPT 대화에서 파악되는 가족과 충석의 캐릭터 특징 데이터를 정리.
- 조치: 관련 대화 코퍼스와 주요 원문을 분석해 충석·보미·태희·세희별 사실/관찰, 해석, 강점, 취약 가능성, 가족 역동을 종합.
- 결과: `충석/가족/가족 캐릭터 특징 분석.md` 생성, 가족 허브와 `충석/충석.md`에 연결, 사람별 노트에 `캐릭터 특징 요약` 섹션 추가.

### 작업 기록 - OpenClaw 런타임 아카이브

- 연결: [[Hermes/Hermes]], [[Hermes/wiki/entities/openclaw-telegram-bots]], [[Hermes/wiki/references/openclaw-to-hermes-migration]], [[Hermes/wiki/references/openclaw-runtime-lessons/README]], [[Hermes/wiki/references/openclaw-runtime-lessons/gog-keyring-wrapper]]
- 요청: [[OpenClaw]] gateway 종료 후 남은 런타임 디렉터리 `~/.openclaw`를 아카이브 처리.
- 사전 확인: `openclaw-gateway.service`는 `inactive`, 실제 OpenClaw 프로세스는 없음. `hermes claw cleanup`의 `pgrep -f openclaw` 경고는 실행 명령 문자열 자체를 잡은 false positive로 판단.
- 조치: `hermes claw cleanup --source /home/brienz311/.openclaw --yes` 실행.
- 결과: `/home/brienz311/.openclaw` → `/home/brienz311/.openclaw.pre-migration` 으로 rename archive 완료. 삭제가 아니라 되돌릴 수 있는 이름 변경.
- 검증: 원본 경로는 없음, archive 경로는 존재. Archive 통계는 파일 34,461개, 디렉터리 4,818개. `acpx`, `agents`, `credentials`, `cron`, `logs`, `memory`, `npm` 등 주요 하위 항목 보존 확인.

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
