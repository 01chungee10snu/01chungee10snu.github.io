---
title: "2026-05-26; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-05-26
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
source: "Obsidian/Hermes/daily/2026-05-26.md"
---

# 2026-05-26; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-05-26|2026-05-26 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-05-26에는 기록를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 기록

- 00:02경 충의 요청으로 [[Bebsu]] 전체 앱 테마/분위기 에셋을 제작하고 반영했다.
- `/mnt/c/Github/Bebsu/scripts/build_theme_assets.py`를 추가해 기존 `Bensu/Asset` 크롭 아이콘 세트에서 전역 배경, 로딩 엠블럼, 프로필 벽지, 방/학습/부모/보상 화면 배경, contact sheet를 생성하도록 했다.
- 산출물은 `Bensu/Asset/theme/`와 `public/assets/bebsu/theme/`에 저장했고, 앱에서는 `src/App.tsx`의 CSS 변수와 `src/styles.css`를 통해 접근 화면, 로딩, 프로필, 학생 방, 문제풀이, 대시보드, 보상 이벤트, 빈 상태에 연결했다.
- 검증: `npm run build`, `GITHUB_PAGES=true npm run build` 통과. 확인용 [[Vite]] dev server는 `http://localhost:5180/`에 detached로 유지했다.
- 00:38경 [[Bebsu]] 전체 에셋 배치와 페이지 흐름을 브라우저 자동화로 점검했다. [[Hermes]] 브라우저 도구는 로컬 URL 정책 차단이 있어 로컬 Chromium/Playwright 경로로 대체했고, Supabase 쓰기 없이 fixture 응답으로 프로필, 학생 방, 문제 제시, 정답/해설/보상, 부모 화면, 오답노트를 데스크톱/모바일에서 테스트했다.
- 점검 중 모바일 학습 화면에서 입력칸 자동 포커스와 화면 전환 스크롤이 문제 제시 상단 경험을 방해할 수 있어 `src/App.tsx`에서 학습/오답 입력 자동 포커스를 제거하고 주요 화면 전환 시 스크롤 리셋을 보강했다. 검증: `npm run build`, `python3 -m pytest tests/test_kma_pool_structured.py`, `BEBSU_TEST_URL=http://127.0.0.1:5176/ node tmp/bebsu-visual-layout-check.spec.mjs` 통과.
- 06:49 pre-compaction flush: 충이 [[Bebsu]] 전체 루프를 원본 이미지와 같은 분위기로 맞춰 달라고 요청했고, 전체 페이지 흐름의 시각 톤을 통일하는 작업을 완료했다.
- 주요 반영 범위: 온보딩/프로필/학생 방/학습 루프/정답 피드백/보상 이벤트/부모 화면/오답노트까지 `Bensu/Asset` 기반 배경·패널·장식 에셋과 CSS 톤을 일관되게 연결했다. 결과 요약과 미리보기 이미지 2개를 Telegram으로 보냈다.

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
