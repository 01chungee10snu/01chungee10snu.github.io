---
title: "2026-06-19; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-06-19
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - 업무자동화
  - 데이터분석
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-06-19.md"
---

# 2026-06-19; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-06-19|2026-06-19 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-06-19에는 작업 기록를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 작업 기록

- [[KoreanNemotron]] 시뮬레이터의 이전 마스코트/이미지 생성 후보 산출물을 정리했다. `sim/frontend/artifacts/`에는 새 패키지 `hnp-lacy-redraw-oneframe/`만 남겼고, Hermes generated의 이전 `yonggangi_walk_8f`도 삭제했다.
- 새 방식 기준을 적용했다: 팔/다리 컷아웃 레이어를 움직이는 방식이 아니라, 원본 참조 기반의 단일 전체 포즈 프레임을 기준으로 하고 이후 프레임도 한 장씩 다시 그려 영상처럼 재생하는 방향으로 전환했다.
- 새 산출물: `sim/frontend/artifacts/hnp-lacy-redraw-oneframe/`. 주요 파일은 `frames/hnp_lacy_redrawn_frame_00_48x72.png`, `char_6_hnp_lacy_redrawn_oneframe_sheet_candidate.png`, `hnp_lacy_oneframe_playback_preview.mp4`, `original_reference_vs_new_redrawn_frame.png`.
- 검증: `ffprobe`로 MP4가 `384x576`, `12fps`, `2.0s`, `24 frames`임을 확인했다. `sim/frontend/artifacts/` top-level은 `hnp-lacy-redraw-oneframe/`만 남았다.
- 정정: [[GPT Imagen]] frame_01 방향은 원본 정체성이 틀어져 폐기했다. 충의 피드백에 따라 최초 원본 캐릭터 자체를 다시 추출해 직접 픽셀화했다. 새 기준 폴더는 `sim/frontend/artifacts/source-character-pixelization-v1/`이며, 이전 `hnp-lacy-redraw-oneframe/` 패키지는 삭제했다. 직접 픽셀화 비교 결과 `48x72`는 얼굴/작업복/H 디테일 손실이 커서 보조안으로만 두고, `64x96`을 권장 기준으로 채택했다. 주요 산출물: `04_pixelized_character_64x96.png`, `char_6_source_pixelized_RECOMMENDED_64x96_sheet.png`, `recommended_64x96_repeated_strip_x5.png`, `pixelization_size_decision_board.png`. 검증: 권장 MP4 `320x480`, `12fps`, `2.0s`, `24 frames`; artifacts top-level은 `source-character-pixelization-v1/`만 남았다.
- 다음 단계로 `64x96` 원본 픽셀화 기준에서 `frame_01`을 전체 포즈 변형으로 제작했다. 컷아웃/분리 레이어 없이 전체 bitmap을 미세하게 기울이고 내려앉히는 방식이며, 원본 U홈/방울/볼/작업복/짧은 발 정체성을 유지한다. 산출물: `frames/frame_00_source_pixelized_64x96.png`, `frames/frame_01_fullpose_shift_64x96.png`, `frame00_01_fullpose_compare_x5.png`, `frame00_01_fullpose_repeated_strip_x5.png`, `frame00_01_fullpose_playback.mp4`, `char_6_source_pixelized_64x96_frame00_01_sheet.png`. 검증: MP4 `320x480`, `12fps`, `4.0s`, `48 frames`; GIF는 8프레임. 움직임은 작지만 정체성 보존 기준으로 적합하며 다음은 frame_02에서 반대 방향/중립 포즈를 추가하면 된다.
- 정정: 충이 원하는 방식은 전체 bitmap 기울임이 아니라, 최초 원본 픽셀화 캐릭터에서 팔/다리를 조금씩 움직이는 장면을 한 장씩 새로 그리는 것이다. 이에 따라 `redraw-limbs-frame01/`에서 후보 A/B/C를 만들었고, A는 팔/작업복 변화가 과하고 B는 손/발이 커서 폐기, C를 채택했다. C는 얼굴/몸/작업복을 유지하고 작은 손/발만 원본 위치 근처에서 새 픽셀 도형으로 다시 그린다. 산출물: `redraw-limbs-frame01/frame_01C_redrawn_tiny_step_64x96.png`, `frame00_01C_redrawn_tiny_step_compare_x5.png`, `frame00_01C_redrawn_tiny_step_strip_x5.png`, `frame00_01C_redrawn_tiny_step_playback.mp4`, `char_6_source_pixelized_64x96_redrawn_tiny_step_00_01_sheet.png`. 검증: MP4 `320x480`, `12fps`, `4.0s`, `48 frames`; GIF는 8프레임.
- 폐기: 충의 지시에 따라 [[HnP Lacy]] 캐릭터 추출/픽셀화/고해상도 4프레임 시안 산출물을 모두 삭제했고, 그 전에 만들었던 이전 마스코트/캐릭터 산출물과 런타임 반영 흔적까지 정리했다. 삭제/원복 범위: `sim/frontend/artifacts/` 전체 관련 산출물, `~/.hermes/profiles/try/generated` 관련 산출물, `public/assets/pixel-agents/mascot/orange_h_mascot_concept.png`, `public/assets/pixel-agents/characters/char_6.png`, `dist/` 빌드 산출물, `pixelAgentAssets.json`의 `char_6` 등록, `BootScene.ts`/`OfficeScene.ts`의 마스코트 전용 프레임/스케일 로직, `verify_visual_contracts.py`의 마스코트 예외 로직. 검증: `char_6`/`orange_h_mascot`/`MASCOT`/`mascot`/`npcFrame`/`npcSprite` 검색 0건, `sim/frontend/artifacts` 비어 있음, `python3 sim/tools/verify_visual_contracts.py` 통과(`6 character sheets at (112, 96)`).

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
