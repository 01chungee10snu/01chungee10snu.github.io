---
title: "2026-05-30; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-05-30
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
source: "Obsidian/Hermes/daily/2026-05-30.md"
---

# 2026-05-30; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-05-30|2026-05-30 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-05-30에는 작업 기록를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 작업 기록

- [[autoclawsnu]] 약탈적/논쟁적 OA 스크리닝 결과의 전체 비중을 `27,666편` 기준으로 재확인했다. 공개 약탈적 저널 exact는 `31편(0.1121%)`, strict any tier는 `41편(0.1482%)`, [[MDPI]] watchlist는 `1,477편(5.3387%)`, Frontiers watchlist는 `549편(1.9844%)`, MDPI 또는 Frontiers는 `2,026편(7.3231%)`, 공개 exact + MDPI/Frontiers 전체 위험군은 `2,057편(7.4351%)`로 정리했다. 기존 결론처럼 MDPI/Frontiers는 자동 제외가 아니라 논쟁적 OA 수동검토 플래그로 해석한다.

- 08:21 [[autoclawsnu]] 통합 분류 CSV에 약탈적 저널 여부 컬럼을 추가했다. 산출물은 `/mnt/c/Github/autoclawsnu/runs/target_method_row_codex_20260528/wos_riss_integrated_target_method_codex_rows_with_predatory_flags.csv`이며, `27,666`행 `71`컬럼이다. `약탈적_저널_해당여부`는 공개 predatory list recommended exact 기준 `31`건, `MDPI_Frontiers_논쟁적_OA_watchlist_해당여부`는 별도 수동검토 플래그 `2,026`건, 통합 스크리닝 플래그는 `2,057`건이다.

- [[Hermes/wiki/references/zai-exec-cli]] 자산을 만들었다. `/home/brienz311/.local/bin/zai-exec`는 [[Z.AI]]/[[GLM]] API를 one-shot CLI 백엔드처럼 호출해 stdout으로 결과를 반환한다. Hermes skill `zai-exec`도 `/home/brienz311/.hermes/profiles/work/skills/mlops/zai-exec/`에 등록했고, 복구용 bundled script는 `scripts/zai-exec`에 보관했다. API key는 채팅/인자에 두지 않고 `GLM_API_KEY`/`ZAI_API_KEY`/`Z_AI_API_KEY` 환경변수로만 읽는다.

- [[Hermes/wiki/entities/Bebsu]] 레포 `/mnt/c/Github/bebsu`의 남은 보상/꾸미기 루프 작업을 완료했다. 추가 내용: `apply_companion_decay` Supabase RPC migration, `loadCompanionDisplay` 호출 전 감쇠 적용, 앱 활성/복귀 시 방 상태 주기 새로고침, 상점 구매 직후 비식품 아이템 자동 장착, 뱁수+착용 아이템 단일 canvas 합성 이미지 렌더링. 검증: `python3 -m unittest tests.test_app_structure tests.test_reward_shop_catalog` 통과, `npm run build` 통과(기존 Vite chunk-size warning만 표시).


## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
