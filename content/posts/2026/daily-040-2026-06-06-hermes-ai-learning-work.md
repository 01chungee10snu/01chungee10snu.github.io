---
title: "2026-06-06; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-06-06
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
source: "Obsidian/Hermes/daily/2026-06-06.md"
---

# 2026-06-06; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-06-06|2026-06-06 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-06-06에는 작업 기록를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 작업 기록

### SNU 연구: AI·로보틱스 통합적 문헌고찰 검색식 2차 초안
- [[SNU👨🎓/연구 Idea 통합]] 18번 섹션에 [[WoS]], [[Scopus]], [[RISS]]/[[KCI]] 파일럿용 검색식 2차 초안을 추가했다.
- 방향은 [[OpenAlex]] seed에서 과다하게 섞인 교육·일반 AI 전망 문헌을 줄이기 위해 `work*`, `employee*`, `workplace`, `organization*`, `occupation*`, `job*`, `task*` 축으로 일터/직무 맥락을 강화하는 것이다.
- 검색식 묶음은 통합 검색식, [[생성형 AI]] 활용역량, [[에이전틱 AI]]/AI agents, Human-AI collaboration, [[로보틱스]]/HRC, [[직무대체가능성]]·자동화 불안, [[적응전문성]]·재교육, 기술 유형 비교, 제외어 후보로 나누었다.
- 이어서 [[autoclawsnu]]에서 [[WoS]]와 [[RISS]] 양쪽 수집 가능성을 점검했다. WoS는 `WOS_API_KEY` 기반 Starter API 수집 스크립트가 있고, RISS는 로그인 없이 검색결과 HTML direct parsing 수집 스크립트가 있어 둘 다 파일럿 수집 가능하다. 다만 WoS 브라우저 full export는 기관 인증/브라우저 상태에 따라 사람 개입이 필요할 수 있어 API fallback을 우선한다.
- 실제 수집을 실행해 `/mnt/c/Github/autoclawsnu/runs/ai_robotics_integrative_review_20260606_all/`에 [[WoS]] raw 3,952건/dedup 3,885건, [[RISS]] raw 326건/dedup 289건, 통합 raw 4,278건/dedup 4,174건을 확보했다. Obsidian 복사본은 `SNU👨🎓/문헌리스트/ai-robotics-integrative-review_wos-riss_dedup_2026-06-06.csv`와 `AI-로보틱스 통합적 문헌고찰 WoS-RISS 수집 요약 2026-06-06.md`에 저장했다.
- 수집 검증 후 RISS 쪽은 단순 통합검색(`isDetailSearch=N`)보다 상세검색(`isDetailSearch=Y`, `fsearchMethod=searchDetail`, `isFDetailSearch=Y`)을 활용해야 한다고 판단했다. RISS 상세검색 필드는 `znTitle`(논문명), `znSubject`(주제어), `znAbstract`(초록), `znAll`(전체) 등을 AND/OR/NOT로 조합할 수 있으므로, 다음 RISS 보강 수집은 제목/주제어에는 기술어를, 초록/전체에는 직무·조직·고용불안·수용/저항 맥락어를 분리해서 적용한다.


## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
