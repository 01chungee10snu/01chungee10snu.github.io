---
title: "2026-05-25; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-05-25
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - 가족-일상
  - HRD-리더십
  - 데이터분석
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-05-25.md"
---

# 2026-05-25; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-05-25|2026-05-25 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-05-25에는 기록를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 기록

- 00:01 KST, 충이 태희·세희용 [[수학학습 앱]]에서 [[IRT]] 기반 출제가 가능한지 질문했다. 현실적 접근은 처음부터 완전한 2PL/3PL 보정보다 Rasch/1PL 기반 난이도 추정과 적응형 출제로 시작하고, 풀이 데이터가 쌓이면 문항 난이도와 학습자 능력치를 보정하는 방식이다.
- 09:32 KST, 충이 [[ttak]] 스킬을 활용해 [[수학학습 앱]]의 설계서, 문항 데이터 구조, 출제 흐름을 잡자고 했다. 이에 프로젝트 허브와 [[Ttak 하네스]], [[제품 설계서]], [[문항 데이터 구조]], [[출제 흐름]], [[다음 구현 계획]]을 생성했다.
- 09:46 KST, 충이 [[ttak]] 인터뷰 질문에 답했다. 결정은 습관 형성+약점 보완, 태희·세희 동시 지원, 10/20 이하 덧셈·뺄셈, 숫자 입력형+객관식, 정답 미공개 오답노트, 별·스티커 표시, 웹 공개 자료 중심 문항 후보 수집, 단순 비밀번호, 기능 MVP 후 디자인 적용이다. `웹 공개 자료 중심`은 저작권·품질 리스크가 있어 [[인터뷰 결정사항]]과 [[리스크 검토]]에 출처·라이선스·재작성·검수 게이트를 명시했다.
- 11:33 KST, 충이 [[Supabase]] MCP를 계정과 연동하라고 했다. `supabase` MCP 서버를 `https://mcp.supabase.com/mcp?read_only=true`로 등록하고, Windows 브라우저에서 GitHub 로그인 기반 OAuth를 완료했다. `codex --enable rmcp_client mcp list` 기준 Auth가 OAuth로 확인됐다. 아직 project_ref 제한은 걸지 않았으므로 [[수학학습 앱]] 프로젝트 ref가 생기면 연결을 좁히는 것이 안전하다.
- 11:43 KST, Windows 브라우저에서 [[Supabase]] 대시보드를 직접 확인했다. 기존 프로젝트 `maTH-adventure`가 있고 Project ref는 `gegwjdcxcarmopiaknwj`였다. 중복 프로젝트 생성을 피하고 `supabase` MCP URL을 `https://mcp.supabase.com/mcp?project_ref=gegwjdcxcarmopiaknwj&read_only=true`로 좁힌 뒤 OAuth를 다시 완료했다. `codex --enable rmcp_client mcp list`에서 Auth가 OAuth로 확인됐다.
- 11:46 KST, compaction 직전 상태 점검. 현재 [[Supabase]] MCP는 `maTH-adventure` 프로젝트(`gegwjdcxcarmopiaknwj`)에 read-only로 제한되어 있다. 다음 단계에서 DB 스키마를 조회하거나 설계 검토는 가능하지만, migration 적용이나 테이블 생성 전에는 write 권한 연결 또는 `read_only=true` 해제가 별도로 필요하다.
- 11:46 KST, 보안 감사 참고사항: `codex-exec-backend` 스킬에서 `child_process` 기반 shell 실행 패턴이 감지되어 검토 권장. WARN으로는 `gateway.trustedProxies` 미설정, Telegram 그룹 allowlist+sandbox off 조합의 신뢰 경계, `brave`/`codex` 플러그인 npm 버전 미고정이 보고됐다. 즉각 조치가 필요한 변경은 아니지만 [[Hermes]] 운영 보안 점검 때 다시 확인할 것.
- 11:45 KST 이후, 충이 다음 단계 진행에 동의해 처음에는 `/mnt/c/Github/maTH`에 [[Supabase]] migration 초안을 만들었으나, 이후 "그 리포지토리 말고 새로운걸 만들어야해 Bebsu로 해줘"라고 정정했다. 새 private GitHub repo `01chungee10snu/Bebsu`와 로컬 경로 `/mnt/c/Github/Bebsu`를 만들고, 설계 문서와 migration을 `Bebsu`로 옮긴 뒤 `maTH`에 잘못 만든 두 파일은 정리했다.

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
