---
title: "2026-06-02; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-06-02
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
source: "Obsidian/Hermes/daily/2026-06-02.md"
---

# 2026-06-02; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-06-02|2026-06-02 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-06-02에는 작업 기록를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 작업 기록

- 00:25 [[Bebsu]] 앱의 이미지 전면 재생성 이후 검증 체계를 강화했다. [[Codex]] goal 실행은 장시간 실행/중단 이슈가 있어 결과를 직접 이어받아 project-local harness를 구현했다. 추가된 검증은 GPTImaGen raw/runtime asset pack, paper-doll 착용 PNG 256x256 transparent canvas/alignment, visual design hooks, asset performance budget이며, `.openclaw/harness/skills/`와 `.openclaw/harness/agents/`에 전용 skill/agent 문서도 추가했다. 검증 결과 `python3 -m pytest -q tests/test_item_asset_harness.py tests/test_app_structure.py tests/test_bebsu_asset_design_harnesses.py`는 10 passed, `npm run build` 성공, 신규 4개 harness 모두 PASS였다. Paper-doll alignment matrix는 Pillow 미설치 환경에서도 dependency-free fallback PNG `.openclaw/harness/_workspace/paperdoll_alignment_matrix.png`를 생성하도록 보완했다. Commit/push 완료: `b174992f967f` (`test: add Bebsu asset design harnesses`).
- 06:45 [[Bebsu]] 상점 `옷장` 탭의 wearable thumbnail이 단독 아이콘처럼 보이던 문제를 수정했다. `ShopItemIcon`이 food가 아닌 slot item을 `.shop-wearable-preview` 안에서 base 뱁수 + wearable/background layer로 보여주도록 변경했고, CSS preview frame 및 regression test를 추가했다. 검증: `npm run build` PASS, `python3 -m pytest -q tests/test_item_asset_harness.py tests/test_app_structure.py tests/test_bebsu_asset_design_harnesses.py` 11 passed, visual design harness PASS, asset performance budget PASS, browser DOM에서 `.shop-wearable-preview=27`, `.wearable-icon=0` 확인. Commit/push 완료: `4a209f42dbe9` (`fix: preview shop wearables on Bebsu character`). 상세 기록: [[Hermes/wiki/references/bebsu-shop-wearable-preview-2026-06-02]].
- 07:40 [[Bebsu]] 상점 UX를 재정리해 `옷장` 탭은 캐릭터 착용 preview가 아니라 standalone product icon을 보여주도록 변경했다. 실제 옷장/방 character preview는 DOM 레이어가 아니라 canvas에서 합성한 single data-URL image를 유지하되, `drawProtectedWearableLayer`로 body item은 하단 영역, hat item은 상단 영역만 그리도록 clip해 앞치마/모자류가 얼굴을 가리는 문제를 완화했다. 검증: `npm run build` PASS, `python3 -m pytest -q tests/test_item_asset_harness.py tests/test_app_structure.py tests/test_bebsu_asset_design_harnesses.py` 12 passed, visual design harness PASS, asset performance budget PASS, browser DOM에서 `.shop-product-icon=27`, `.shop-wearable-preview=0`, `.wearable-icon=0`, closet `.bebsu-composited-image` data PNG 확인. Commit/push 완료: `7cc624aa2900` (`fix: show shop products and protect equipped Bebsu`). 상세 기록: [[Hermes/wiki/references/bebsu-shop-product-icons-composited-equipment-2026-06-02]].
- 14:00 [[Bebsu]] 뱁수가 먹이를 먹지 않으면 상태/기분 스테이터스와 이미지가 함께 낮아지도록 effective care state를 보정했다. `effectiveMoodFor`와 `effectiveCompanionCareStateFor`를 추가해 fullness뿐 아니라 mood도 시간 경과에 따라 낮추고, room의 상태/기분/care prompt와 `bebsuStateVisualFor` 이미지 state가 같은 기준을 쓰게 했다. `last_decay_at`을 view/type/service에 연결하고 적용용 migration `202606020001_companion_display_last_decay_at.sql`을 추가했다. 검증: `npm run build` PASS, 관련 pytest `21 passed, 1 skipped, 2 subtests passed`, visual design harness PASS, asset performance budget PASS, browser smoke에서 hungry brown baby image/state/prompt 확인. Commit/push 완료: `9c82f0c2092e` (`fix: decay Bebsu mood visuals over time`). 상세 기록: [[Hermes/wiki/references/bebsu-companion-decay-visual-state-2026-06-02]].
- [[용강]] 캐릭터 생성을 위한 Hermes 전역 스킬 `yonggang-character-generation`을 `memo` 프로필의 `creative/` 카테고리에 생성했다. 스킬은 [[용강]]을 의인화된 쇳물 방울형 기업 마스코트로 고정하고, U자형 상단 홈·floating droplet·작은 타원 눈·큰 cream cheek·tiny three-curve mouth·no nose 규칙을 hard lock으로 보존한다. GPTImaGen / [[Codex]] image_generation 사용 시 원본 3개 이미지를 참조하도록 경로를 연결했다. 상세 기록: [[Hermes/wiki/references/yonggang-character-generation-skill]].
- [[용강]]의 봄·여름·가을·겨울 정면 복장 variation 4종을 [[GPTImaGen]] / [[Codex]] image_generation 경로로 생성했다. 산출물은 `/mnt/c/Github/Yonggang/generated/seasonal_front_variations_20260602/`에 저장했고, 계절별로 봄(하늘색 작업복+분홍 스카프), 여름(가벼운 조끼+흰 이너), 가을(남색/주황 포인트+베이지 스카프), 겨울(패딩 작업복+크림 트림) 분위기를 적용했다. 상세 기록: [[Hermes/wiki/references/yonggang-seasonal-front-variations-2026-06-02]].
- [[용강]]의 추가 계절 장면 variation 3종을 [[GPTImaGen]] / [[Codex]] image_generation 경로로 생성했다. 산출물은 `/mnt/c/Github/Yonggang/generated/seasonal_scene_variations_20260602/`에 저장했고, 봄 나들이(벚꽃 공원·피크닉), 여름 바캉스(해변·파라솔·튜브), 가을 등산(단풍 산길·지팡이·배낭) 분위기를 적용했다. 세 장 모두 1254×1254 정사각 PNG이며 용강 face/head lock은 유지됐다. 상세 기록: [[Hermes/wiki/references/yonggang-seasonal-scene-variations-2026-06-02]].
- [[용강]]의 turnaround 시도 중 측면모습 산출물이 사용자 기준에 맞지 않아 모두 삭제했다. `/mnt/c/Github/Yonggang/generated/turnaround_variations_20260602/`에는 뒷모습 `back_view.png`만 유지하고, 좌측면·우측면·4-view sheet·height_asymmetry_refine 및 관련 prompt/log/script는 제거했다. 측면 view는 정면 lock만으로 추론하지 않고 승인된 측면 reference 또는 별도 QA cycle이 필요하다고 정정했다. 상세 기록: [[Hermes/wiki/references/yonggang-turnaround-variations-2026-06-02]].

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
