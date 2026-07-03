---
title: "2026-05-21; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-05-21
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - AI-LLM
  - 데이터분석
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-05-21.md"
---

# 2026-05-21; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-05-21|2026-05-21 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-05-21에는 연결 — 일지, 작업 내용, 추가 기록 — 16:43, 추가 기록 — 17:15를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 연결 — 일지

- [[Hermes/daily/일지-허브]]
- [[Hermes]]
- [[Hermes/wiki/references/AI활용우수사례-안될과학-하네스시연회]]
- [[Hermes/wiki/references/하네스-오픈소스-OMO-OMC-OMX]]

### 작업 내용

### 딸깍(ttak) 스킬 제작 — 실증 기반

**배경**: 안될과학 "하네스 딸깍 시연회" 영상 분석 후, OpenClaw 환경에서 비슷한 "딸깍" 경험을 구현하는 스킬 필요성 제기

**실증 테스트 결과**:
- `sessions_spawn` 병렬 실행: ✅ 3개 동시 스폰, 8-48초 내 완료
- Push-based 결과 수신: ✅ 폴링 없이 자동 완료 통보
- 파일 시스템 공유: ✅ 서브에이전트가 생성한 파일 메인에서 읽기 가능

### 추가 기록 — 16:43

### [[ttak]] 기반 PPTX 프로젝트 개선 진행

**대상 리포지토리**: `/mnt/c/github/pptx`

**맥락**: 사용자가 [[GPT image 2.0]]로 만든 슬라이드와 현재 [[ihateppt]]/PPTX 프로젝트가 생성하는 네이티브 슬라이드 사이의 배치·디자인 격차가 크다고 지적했다. 핵심 판단은 "이미지 모델의 미감 자체를 그대로 native PPTX에 이식할 수는 없지만, 레이아웃 토큰·공간감·계층 구조·스타일 규칙을 추출해 렌더러에 반영하면 개선 가능"하다는 것.

**완료된 서브작업**:
- `ttak-design-primitives` 완료.

### 추가 기록 — 17:15

### [[Codex exec]] 기반 [[GPT image 2.0]] benchmark 생성 경로 확정

**맥락**: 사용자가 `C:\Github\GPTImaGen` 프로젝트의 이미지 생성 방식을 참고해, [[codex exec]]에서 [[GPT image 2.0]]를 활용한 slide image benchmark 생성 방법을 탐색하고 성공하면 스킬로 저장하라고 요청했다.

**확인 결과**:
- [[OpenAI API]] 공식 문서 기준으로 GPT Image 모델(`gpt-image-2` 포함)은 Image API와 Responses API `image_generation` built-in tool 경로로 사용 가능.
- `/mnt/c/Github/GPTImaGen`은 OpenAI SDK/API 키를 직접 쓰지 않고 `codex exec --enable image_generation`를 backend worker로 호출한다.
- Linux OpenClaw 쪽 Codex(`codex-cli 0.64.0`)에는 `image_generation` feature가 없었다.

### 추가 기록 — 17:42

### [[Openclaw Cron]] AI 최신정보 아침 요약 추가

**요청**: 매일 아침 7시에 [[OpenAI]], [[Google Gemini]], [[Claude]] 공식 블로그/뉴스를 확인해 최신 정보를 요약 보고.

**등록 결과**:
- Cron ID: `e90c8ca1-5da3-469b-8f77-0fb6b8e0709e`
- 이름: `AI 최신정보 아침 요약`
- 스케줄: `0 7 * * *` @ `Asia/Seoul`, exact

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
