---
title: "2026-06-01; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-06-01
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - AI-LLM
  - 가족-일상
  - HRD-리더십
  - 데이터분석
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-06-01.md"
---

# 2026-06-01; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-06-01|2026-06-01 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-06-01에는 작업 기록를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 작업 기록

- 06:00 자동 기억 정리에서 최근 대화의 [[adaptive expertise]] 연구 방향을 반영했다. [[autoclawsnu]]의 생성형 AI·로보틱스 미래일터 연구는 [[적응전문성]]을 중심개념 후보로 삼되, 단순 유행어가 아니라 AI literacy, lifelong learning, digital competence, career adaptability와 구분되는 “새 기술환경에서 기존 직무지식과 경험을 재구성하는 능력”으로 좁혀야 한다. 추천 모형은 AI·로보틱스 기반 작업환경 노출 → 적응전문성 → 미래 직무준비도/고용가능성/혁신행동이며, 조직학습문화나 심리적 안전감은 조절변수 후보로 둔다.
- 07:32 [[Windows WSL Bridge]] 경유로 [[Codex]] 보고서형 deep research 실행을 재시도했다. WSL의 Codex CLI는 `gpt-5.1-codex`가 ChatGPT 계정에서 지원되지 않아 실패했지만, Windows 쪽 Codex CLI `0.132.0`은 `gpt-5.5`로 정상 인증·실행되었다. 결과 JSON과 UTF-8 보고서는 `C:/Users/Administrator/deep-research-spikes-win/outputs/`에 저장했다. 주제는 [[autoclawsnu]]의 한국 제조업 숙련근로자 작업궤적 데이터셋과 로보틱스 경쟁력 함의다.
- 20:25 [[Windows WSL Bridge]] 방식의 [[Codex]] 보고서형 wrapper를 `/home/brienz311/deep-research-spikes/win_codex_research.py`로 작성했다. 한글 프롬프트 전달은 PowerShell에서 UTF-8 prompt 파일을 stdin으로 넘기는 방식으로 검증했고, 최종 보고서는 `C:/Users/Administrator/deep-research-spikes-win/runs/20260601-201739-한국_제조업_숙련근로자_작업궤적_데이터뱅크를_통한_로보틱스_경쟁력_강화_방안/report.utf8.md` 및 과제 폴더 `대한민국_제조업_숙련근로자_작업궤적_데이터뱅크_DeepResearch_보고서.md`에 저장했다.
- 22:59 [[Bebsu]] 앱 이미지 전면 재생성 작업을 기록했다. 앱 참조 이미지 세트를 점검하고 [[GPTImaGen]] 기반으로 뱁수 캐릭터 상태, 상점 착용 아이템, 음식, 테마, UI 이미지를 새로 생성·최적화해 반영했다. 원본 60개는 `/mnt/c/Github/Bebsu/Bensu/Asset/gptimagen/bebsu/raw/`, 런타임 에셋 94개는 `/mnt/c/Github/Bebsu/public/assets/bebsu/`에 있으며, 테스트 `17 passed, 4 subtests passed`, build 성공, 최종 HEAD는 `9e3538159cd7faad4da96ccf40b67f09c6f889ec`다. 상세 기록: [[Hermes/wiki/references/bebsu-gptimagen-assets-2026-06-01]].
- 23:08 Telegram에서 논의한 [[Adaptive Expertise]] 중심의 생성형 AI·로보틱스 미래일터 연구 아이디어를 [[SNU👨🎓/연구 Idea 통합]]의 `14. Adaptive Expertise 중심의 생성형 AI·로보틱스 미래일터 연구` 섹션으로 저장했다. 핵심은 특정 도구 숙련이 아니라 AI·로보틱스 통합 일터에서 기존 직무지식과 경험을 재구성하는 전문성 재구성 능력이며, SSCI급 검토 기준으로 인접 개념과의 구분, 매개모형, 이론 프레임, 제목 후보, 심사자 공격 지점, 측정 문항 방향을 함께 기록했다.
- 23:15 [[Adaptive Expertise]] 연구 수행 순서와 추가 문헌 수집 필요성을 검토했다. 현재 [[autoclawsnu]] 통합 리스트는 27,666행까지 AI 대상·방법 분류가 완료되어 있어 생성형 AI 지형 파악에는 충분하지만, 적응전문성 중심 연구세계 구축에는 broad GenAI 추가 수집보다 적응전문성·전문성/전이·human-AI/robot collaboration·future work readiness·측정척도 문헌의 목표형 보강이 필요하다고 정리했다.

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
