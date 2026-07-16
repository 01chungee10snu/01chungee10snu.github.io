---
title: "2026-07-03; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-07-03
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - AI-LLM
  - 업무자동화
  - 데이터분석
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-07-03.md"
---

# 2026-07-03; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-07-03|2026-07-03 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-07-03에는 작업 기록를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 작업 기록

- [[Zotero]] [[PRISMA]] [[숙련 노후화]] 문헌노트 PDF attachment 연결 완료(2026-07-03 KST): `/Users/01chungee10/snu_seed_search/extracted_metadata/_zotero_import_results.json`의 17개 parent item에 로컬 PDF 17개를 Zotero child attachment로 연결했다. DB 백업은 `/Users/01chungee10/snu_seed_search/zotero_attach_work/zotero.sqlite.pre_attach.20260703_234944.bak`, 실행 manifest는 `/Users/01chungee10/snu_seed_search/zotero_attach_work/attach_run_manifest.20260703_234944.json`, 검증표는 `/Users/01chungee10/snu_seed_search/zotero_attach_work/attachment_verify_table.json`이다. 검증: `PRAGMA integrity_check` ok, 17개 attachment DB row/storage file/SHA-256 일치, Zotero 재기동 후 local connector ping 200. Obsidian `[[SNU👨🎓/참고문헌/PRISMA_Automation_Skills/00_Synthesis_Matrix]]` 및 17개 개별 문헌 노트에 child PDF key와 `zotero://select/items/<attachmentKey>` 링크를 반영했다.
- [[Seed Paper]] [[PRISMA]] [[숙련 노후화]] 핵심 seed 12편 PDF 확보 최종 검증(2026-07-03 KST): `/Users/01chungee10/snu_seed_search/seed_paper_reclassification.csv`에서 `tier == 필수 seed`인 12편을 재확인하고 `/Users/01chungee10/snu_seed_search/core_seed_papers_12`에 유효 PDF 11개를 확보했다. 기존 로컬 PDF 매칭 8건, 공개 경로 다운로드 3건이 `%PDF-` 매직 바이트·파일 크기·SHA-256 manifest 일치 검증을 통과했다. 13번 [[Modeling the Skills Obsolescence Process]]는 JSTOR/AOM 직접 PDF URL이 HTTP 403을 반환하고 OpenAlex 기준 `open_access.is_oa=false`, `pdf_url=null`, `has_fulltext=false`라 접근 제한 잔여 항목으로 분리했다. 산출물: `/Users/01chungee10/snu_seed_search/core_seed_papers_12_report.md`, `/Users/01chungee10/snu_seed_search/core_seed_papers_12_manifest.json`, `/Users/01chungee10/snu_seed_search/core_seed_papers_12_manifest.csv`, `/Users/01chungee10/snu_seed_search/core_seed_papers_12_final_verification.md`. 검증: `python3 secure_core_seed_papers.py` 재실행은 미확보 1건을 의미하는 설계 반환값 `exit 2`와 `MISSING_INDEXES=13`을 출력했고, 별도 감사에서 확보 11개 PDF 검증 이슈 0건 및 secret scan findings 없음.
- [[Seed Paper]] [[PRISMA]] [[숙련 노후화]] 서지/DOI/역할 검증 및 다음 검색식 산출(2026-07-03 17:33 KST): `/Users/01chungee10/snu_seed_search/seed_paper_reclassification.csv`의 32편을 재검증해 필수 seed 12편, 보조 seed 13편, 주변 참고 7편으로 확정했다. DOI 상태는 `verified` 22편, `verified_translation_title` 2편, `web_verified_kci_crossref_unindexed` 2편, `no_doi` 6편이며, 제목 기반 no-DOI 재검색 감사는 `/Users/01chungee10/snu_seed_search/no_doi_title_search_audit.json`에 남겼다. 최종 산출물은 `/Users/01chungee10/snu_seed_search/seed_paper_verify_next_search.md`, 실행용 검색식 CSV는 `/Users/01chungee10/snu_seed_search/seed_paper_next_search_queries.csv`, 재현 스크립트는 `/Users/01chungee10/snu_seed_search/make_verify_next_search.py`다. 검증: `py_compile` 및 생성 스크립트 실행 성공, seed rows 32/필수 12/query 10 검증, secret scan findings 없음, `VALIDATION_PASS`. 다음 검색 우선순위는 Scopus/WoS Q1·Q2·Q3·Q6·Q7·Q8 → KCI/RISS/DBpia/KISS Q7·Q8 → 필수 seed 중심 citation chaining Q10 순서로 기록했다.
- [[HR after AI 2026]] [[Gmail]] 요약메일 추가 전달 확인(2026-07-03 13:59 KST): 사용자가 HR after AI 요약메일을 현대제철 추가 수신자에게도 보내달라고 요청했다. Gog Gmail sent 검색으로 `to:serapina@hyundai-steel.com`, subject `[HR after AI 2026] 연사별 키워드·토픽 중심 상세 정리 (Graph View 수정본)` 메일이 2026-07-03 13:57 KST에 발송된 것을 확인했다. Gmail thread id는 `19f2031152ee49f6`, 해당 thread의 messageCount는 2이며 중복 발송을 피하기 위해 추가 재발송은 하지 않았다.
- [[Hermes/Hermes]] [[TOSS]] [[한국투자증권]] live-submit 장전 주문 차단 보강(2026-07-03 05:05 KST): 사용자가 “시장은 9시에 열린다”고 지적해 `toss-ttak-loop`의 실주문 실행 시각과 코드 가드를 보수적으로 수정했다. Cron `toss-ttak-loop`(`9826e4d8dc8e`)은 평일 09:01 KST(`1 9 * * 1-5`)로 설정되어 다음 실행이 `2026-07-03T09:01:00+09:00`임을 확인했다. `src/toss_alpha/execution/live_submit.py`에는 KST 정규장 시간 gate를 두어 `dry_run=False` 실주문은 09:00 KST 전 HTTP submit 이전에 fail-closed로 차단되도록 했고, `tests/test_live_submit.py`에는 pre-open real submit이 HTTP를 호출하지 않는 회귀 테스트를 추가했다. `AGENTS.md`에도 live order 허용 조건에 “09:00 KST 전 BUY submit 차단”을 명시했다. 검증: `PYTHONPATH=/Users/01chungee10/Github/TOSS/src /Users/01chungee10/Github/TOSS/.venv/bin/python -m pytest tests/test_live_submit.py tests/test_live_execution_readiness.py -q` → 18 passed.
- [[TOSS]] [[한국투자증권]] 실계좌 read-only 잔고 조회 및 상품코드 보정(2026-07-03 08:53 KST): KIS `inquire-balance`를 주문 없는 read-only 경로로 실행했다. `ACNT_PRDT_CD=21`은 `APAC0489` “위탁계좌인 경우만 조회가능”으로 차단되어, 사용자가 알려준 상품코드 `01`로 재조회했다. 결과: `rt_cd=0`, `msg_cd=KIOK0560`, 예수금 `220,000원`, 주식평가금액 `0원`, 총평가금액 `220,000원`, 보유종목 0개. 증거 파일: `/Users/01chungee10/Github/TOSS/reports/harness/kis_account_balance_20260703T085319+0900.json`. 실전 wrapper 기본값도 `KIS_ACNT_PRDT_CD=01`로 보정했고 `bash -n` 통과, live readiness는 `ready: True`, `missing: []`, 회귀 테스트 `tests/test_kis_readonly_connector.py tests/test_live_submit.py tests/test_live_execution_readiness.py` → 23 passed.
- [[TOSS]] [[한국투자증권]] 실주문 접수 후 체결/잔고 확인(2026-07-03 12:41 KST): 10:27:45 KST 접수된 BUY 3건의 KIS 현황을 read-only로 재조회했다. 주문 조회 `inquire-daily-ccld` 결과 `307930` [[컴퍼니케이]] 9주 지정가 6,000원은 전량 체결(`tot_ccld_qty=9`, `rmn_qty=0`, 체결금액 54,000원)됐고, `032500` [[케이엠더블유]] 3주 지정가 16,170원 및 `308080` [[바이젠셀]] 10주 지정가 5,470원은 미체결 잔량이 각각 3주/10주로 남아 있다. 잔고 조회 결과 보유 1종목, 컴퍼니케이 9주, 평가 54,090원, 평가손익 +90원(+0.16%), 총평가금액 220,020원. 증거 파일: `/Users/01chungee10/Github/TOSS/reports/harness/kis_live_status_20260703_now.json`, `/Users/01chungee10/Github/TOSS/reports/harness/kis_order_status_20260703_now.json`.
- [[TOSS]] [[한국투자증권]] [[컴퍼니케이]] 장마감 전 실적 재조회 및 전략 리서치 메모 작성(2026-07-03 16:20 KST): KIS read-only 잔고/주문을 다시 확인했다. 잔고 스냅샷은 `/Users/01chungee10/Github/TOSS/reports/harness/kis_live_status_20260703_160238.json`, 주문 스냅샷은 `/Users/01chungee10/Github/TOSS/reports/harness/kis_order_status_20260703_161011.json`. 결과: 총평가금액 221,730원, 현금 220,000원, 보유 1종목 [[컴퍼니케이]] 9주, 평균 6,000원, 현재가 6,200원, 평가손익 +1,800원(+3.33%). 3개 후보 중 체결은 컴퍼니케이 1건뿐이며 계획금액 157,210원 대비 체결금액 54,000원으로 금액 기준 체결률 34.3%. [[케이엠더블유]]와 [[바이젠셀]]은 16:10 KIS 조회 기준 체결 0, 잔량 0, `rjct_qty`가 각각 3/10으로 표시됐다. 전략 판단: promoted walkforward 정책은 `down_high_vol`에서 NO_TRADE였고 aggressive small-account 정책만 후보 3개를 냈으므로, 다음 운용은 promoted policy를 기본 집행 정책으로 두고 aggressive는 paper/manual-draft tier로 낮추며, LLM은 뉴스/공시 JSON event tag와 bad-news veto/alert만 담당하게 한다. 리서치 메모: `/Users/01chungee10/Github/TOSS/reports/harness/toss_strategy_research_20260703.md`.

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
