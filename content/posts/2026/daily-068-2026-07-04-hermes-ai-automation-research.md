---
title: "2026-07-04; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-07-04
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - AI-LLM
  - 업무자동화
  - 데이터분석
  - HRD-리더십
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-07-04.md"
---

# 2026-07-04; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-07-04|2026-07-04 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-07-04에는 작업 기록, 2026-07-04 전체 운영 프로세스 스크립트화 (master_pipeline.py), Zaibot LLM 27B 전환를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 작업 기록

- [[PRISMA]] [[Seed Paper]] [[NotebookLM]] [[Zotero]] [[Obsidian]] PDF→NotebookLM→Zotero→Obsidian 고속 파이프라인을 통합 오케스트레이터로 고정했다(2026-07-04 01:00 KST). 기존 Zotero parent 생성 전용 파일은 발견되지 않아 `/Users/01chungee10/snu_seed_search/prisma_pipeline.py`의 `zotero-create` 단계에 `/connector/saveItems` 기반 parent 생성 로직을 재구현했다. 오케스트레이터는 `discover`, `notebooklm-upload`, `zotero-create`, `zotero-attach`, `obsidian-update`, `verify` 단계를 제공하고 기본값은 dry-run이며 실제 쓰기는 `--run`이 있어야 수행된다. `zotero-attach`는 Zotero local API로 17개 PDF child attachment 존재를 먼저 확인해 이미 완료된 경우 SQLite/storage 스크립트를 건너뛰도록 보강했다. 문서: `/Users/01chungee10/snu_seed_search/README_PRISMA_PIPELINE.md`, 위키 reference: `[[Hermes/wiki/references/prisma-pdf-notebooklm-zotero-obsidian-pipeline]]`. 검증: `python3 -m py_compile prisma_pipeline.py` PASS, `python3 prisma_pipeline.py --steps all --manifest pipeline_runs/prisma_pipeline_dry_run_all.json` PASS, `python3 prisma_pipeline.py --steps verify --check-notebooklm --manifest pipeline_runs/prisma_pipeline_verify_notebooklm.json` PASS. 결과: paper/PDF 17/17, Zotero parent 17, PDF child attachment 17, Obsidian literature note 17, `zotero_pdf_attachment_key` 17, `zotero://select/items/` 링크 17, NotebookLM source list 검증 PASS.
- [[PRISMA]] [[Zotero]] [[NotebookLM]] 선행연구 DB 운영모델을 Hermes skill에 반영했다(2026-07-04). `prisma-pdf-notebooklm-zotero-obsidian-pipeline` 스킬을 개선해 Zotero=문헌 본거지, NotebookLM=추출 엔진, Excel/Notion/Airtable=비교분석 DB 역할 분리를 기본 원칙으로 추가했다. 상세 reference는 `/Users/01chungee10/.hermes/profiles/research/skills/research/prisma-pdf-notebooklm-zotero-obsidian-pipeline/references/literature-db-operating-model.md`에 저장했고, 포함 내용은 Zotero 컬렉션 구조, 접두어 태그 체계, 선행연구 DB 컬럼, NotebookLM 추출 프롬프트, 리스크/대응이다. 검증: 스킬 로드 PASS, frontmatter PASS, secret scan findings 없음.
- [[PRISMA]] [[Zotero]] [[NotebookLM]] [[Excel]] 선행연구 DB Excel export를 완전 script화했다(2026-07-04 02:28 KST). `scripts/export_literature_db_excel.py`는 stdlib만으로 `.xlsx` workbook(5 sheet: 선행연구DB·태그가이드·컬렉션가이드·NotebookLM프롬프트·검증요약)과 UTF-8 BOM `.csv`를 생성한다. 43컬럼 × 17행, Zotero Key 17/17, PDF Attachment Key 17/17, Citation Key 17/17. `prisma_pipeline.py`에 `excel-export` step을 추가해 `--steps excel-export` 또는 `--steps excel-export,verify`로 실행 가능. 검증: xlsx 무결성 PASS(row=18, cell=774), CSV 18행 43컬럼, pipeline 통합 테스트 PASS, secret scan findings 없음.
- [[Hermes/Hermes]] 챗봇 후속 작업 감지(2026-07-03 22:06, `research/telegram`, session `20260703_213314_e87239`): Aside Browser PDF 다운로드 및 인증 상태 점검 #44. 요청 내용: “이어서 계속하세요”; “우선 notebooklm을 통해서 논문에서 추출할 수 있는 메타데이터들을 추출하는 프롬프트를 통해 추출하고 각 문헌별로 정보를 zotero에 연동하여 저장하고 obsidian에서 볼 수 있도록 워크플로우 설계 가능?”; “[Your active task list was preserved across context compression] - [>] notebooklm-create. NotebookLM 인증 복구 후 노트북 생성/재사용…”; “[CONTEXT COMPACTION — REFERENCE ONLY] Earlier turns were compacted into the summary below. This is a handoff from a pre…”
- [[Hermes/Hermes]] 챗봇 후속 작업 감지(2026-07-03 22:07, `work/telegram`, session `20260703_213143_5d5ef8`): 인사말 대화 시작 #16. 요청 내용: “그 데이터까지 고려해서 다시 백테스트 해보세요 그리고 수익을 위한 전략을 채택하여 예상수익률 다시 도출하세요”
- [[Hermes/Hermes]] 챗봇 후속 작업 감지(2026-07-03 22:07, `zai/telegram`, session `20260703_050247_3176f87a`): 터미널 보안 감사 스킬 생성. 요청 내용: “모든 작업 수행하세요. 작업의 방향에 대해서 agy에게 가이드를 받아서 수행하세요.”; “Agy 이용해서 개발안된거 진행”; “네 터미널을 통해서 요청하세요”; “[Replying to: "Agy CLI 에게 현재 워크플로우 프로젝트의 상태와 구현되지 않은 기능들을 파악해달라고 요청하겠습니다. 📋 분석 계획 **1. 기능 요구사항 분석** • 도구: Agy • 설명: 사용자…”
- [[Hermes/Hermes]] 신규 챗봇 작업 감지(2026-07-03 23:09, `work/telegram`, session `20260703_233031_13e22d`): 인사말 대화 시작 #17. 요청 내용: “[Replying to: "백테스트 다시 했습니다. 인버스 데이터를 넣으면 성과가 개선됩니다. 적용한 방식 기존 forward paper 전략에 아래 규칙을 붙였습니다. 평소: 기존 long 전략 유지 macro_…”; “만약 1천만원 대출을 받아서 계속 운영한다면 언제 대출금 갚을 수 있을까?”; “수익이 나면 복리로 붙을텐데 시간이 1년이나 걸려?”; “그러면 1억 대출 받는다 니가 내 도와줘”
- [[Hermes/Hermes]] 신규 챗봇 작업 감지(2026-07-03 23:09, `research/telegram`, session `20260703_231539_c62f60`): Aside Browser PDF 다운로드 및 인증 상태 점검 #46. 요청 내용: “[Replying to: "전체 워크플로우 완료했습니다. 최종 결과를 정리하겠습니다. --- 완료 요약 워크플로우 전 단계 완료 **1. NotebookLM 메타데이터 추출** • 상태: ✅ • 산출물: 17개 논…”; “우선 notebooklm을 통해서 논문에서 추출할 수 있는 메타데이터들을 추출하는 프롬프트를 통해 추출하고 각 문헌별로 정보를 zotero에 연동하여 저장하고 obsidian에서 볼 수 있도록 워크플로우 설계 가능?”; “[Your active task list was preserved across context compression] - [>] notebooklm-create. NotebookLM 인증 복구 후 노트북 생성/재사용…”; “[Your active task list was preserved across context compression] - [>] zotero-attach-discover. Zotero 아이템·PDF·API 상태 확인…”

### 2026-07-04 전체 운영 프로세스 스크립트화 (master_pipeline.py)

### 작업 내용
- `master_pipeline.py` 통합 오케스트레이터 작성 — 검색부터 Excel export까지 6개 Phase를 하나의 스크립트로 통합
- `MASTER_PIPELINE_README.md` 작성 — 전체 프로세스 문서화
- dry-run 검증 PASS — 모든 Phase 정상 인식

### Phase 구조
| Phase | 이름 | 스크립트 | 현재 상태 |
|---|---|---|---|

### Zaibot LLM 27B 전환

- [[Hermes/Hermes]] [[Hermes/wiki/entities/hermes-telegram-bots]] [[Hermes/wiki/entities/chumgeememorybot]] [[Zaibot]] 로컬 LLM을 `Jackrong/MLX-Qwen3.5-9B-Claude-4.6-Opus-Reasoning-Distilled-4bit`에서 `Jackrong/MLX-Qwen3.5-27B-Claude-4.6-Opus-Reasoning-Distilled-4bit`로 전환했다(2026-07-04 KST).
- 사용자가 지정한 HF 모델 `mconcat/Qwen3.5-27B-Claude-4.6-Opus-Reasoning-Distilled-NVFP4`는 `NVFP4/compressed-tensors` 형식으로 NVIDIA/vLLM 계열용이며 Apple Silicon + `mlx-lm` 로컬 Zaibot에는 직접 적용할 수 없어, 동일 계열 MLX 27B 4bit 변환판을 적용했다.
- 수정 파일: `/Users/01chungee10/.hermes/profiles/zai/config.yaml`, `/Users/01chungee10/.hermes/profiles/zai/scripts/run-mlx-qwen35-server.sh`, `/Users/01chungee10/.hermes/profiles/learn/scripts/ensure-zaibot-mlx-qwen35.sh`.
- 검증: `127.0.0.1:8088/v1/models`가 27B 모델을 노출했고, `/v1/chat/completions`에서 `model=Jackrong/MLX-Qwen3.5-27B-Claude-4.6-Opus-Reasoning-Distilled-4bit`, `finish_reason=stop`, content 응답을 확인했다. Watchdog exit code도 0.
- [[Zaibot]] 9B 모델 캐시를 삭제했다(2026-07-04 KST). 삭제 대상: `/Users/01chungee10/.cache/huggingface/hub/models--Jackrong--MLX-Qwen3.5-9B-Claude-4.6-Opus-Reasoning-Distilled-4bit` 및 `.locks` 디렉터리. 회수 용량: 약 4.7GB. 검증: HuggingFace cache 후보 없음, `127.0.0.1:8088/v1/models`는 27B만 노출, Zaibot config 기본 모델도 27B 유지. `/Users/01chungee10/.hermes/profiles/zai/memories/MEMORY.md`의 오래된 9B 참조도 27B로 갱신했다.
- [[Hermes/Hermes]] 신규 챗봇 작업 감지(2026-07-04 06:30, `zai/telegram`, session `20260704_063057_17ef4f18`): [Replying to: "Agy CLI 에게 Workflow Executor 구현을 위한 상세한 기획안을 요청하고, 그 결과를 바탕으로 실제 구현을 진행하겠습…. 요청 내용: “[Replying to: "Agy CLI 에게 Workflow Executor 구현을 위한 상세한 기획안을 요청하고, 그 결과를 바탕으로 실제 구현을 진행하겠습니다. 📋 Executor 구현 계획 **1. 액션 매…”; “[System: The previous response was cut off by a network error mid-stream. Continue exactly where you left off. Do not r…”; “계속”; “작업하세요”
- [[Hermes/Hermes]] 신규 챗봇 작업 감지(2026-07-04 08:15, `work/telegram`, session `20260704_081530_a55b5176`): [Replying to: "안 됩니다. 1억 대출은 지금 구조에서는 막아야 합니다. 숫자로 보면 바로 드러납니다. 현재 자기자본: 221,730원 대출 1억 투…. 요청 내용: “[Replying to: "안 됩니다. 1억 대출은 지금 구조에서는 막아야 합니다. 숫자로 보면 바로 드러납니다. 현재 자기자본: 221,730원 대출 1억 투입 후 운용자산: 100,221,730원 MDD 한 번…”; “이제 이 엔진은 자동거래가 잘 되는 것 맞나? KIS API 호출횟수가 시간당 제한이 있는 것 같던데”
- [[Hermes/Hermes]] 신규 챗봇 작업 감지(2026-07-04 09:28, `research/telegram`, session `20260704_092903_6b4074`): Aside Browser PDF 다운로드 및 인증 상태 점검 #62. 요청 내용: “전체 운영 프로세스가 어떻게 돼? 설명해줘봐”; “엑셀파일로 저장하도록 모두 script화 시킬것”; “[CONTEXT COMPACTION — REFERENCE ONLY] Earlier turns were compacted into the summary below. This is a handoff from a pre…”; “아니 문헌리스트 확보하는 것부터 정리해야지 다운로드”

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
