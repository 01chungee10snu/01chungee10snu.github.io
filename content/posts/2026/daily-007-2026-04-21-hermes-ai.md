---
title: "2026-04-21; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-04-21
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - AI-LLM
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-04-21.md"
---

# 2026-04-21; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-04-21|2026-04-21 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-04-21에는 WoS 키워드 회상, OneDrive 로그인 점검 (brienz311@gmail.com), Obsidian 볼트 전역 경로 설정를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### WoS 키워드 회상

- WoS Query 1: `TS=(("generative AI" OR "generative artificial intelligence" OR ChatGPT OR "large language model*" OR LLM*) AND (literacy OR competency OR competence OR capability OR proficiency OR skill*))`
- WoS Query 2 (미실행 후보): 확장형 — self-efficacy, acceptance, adoption + effect/impact 포함
- 출처: `tmp/run_wos_batch.py`

### OneDrive 로그인 점검 (brienz311@gmail.com)

- 문제: built-in Administrator (SID-500) + UAC 비활성화 (EnableLUA=0) 환경에서 OneDrive 계정 연결 안 됨
- 시도: OneDrive /reset + 재실행 → 프로세스는 올라오나 UserEmail, UserFolder 여전히 비어있음
- 로그 힌트: InteractionRequired, credential invalid, OID claim missing, AccountTypeUnAuthenticated
- 결론: 위험한 레지스트리/UAC 변경 없이는 자동 복구 불가
- 권장: 일반 사용자 계정 생성 후 그 계정에서 OneDrive 로그인
- 참고문서: Microsoft 공식 — built-in admin, UAC Admin Approval Mode, OneDrive reset

### Obsidian 볼트 전역 경로 설정

- 사용자 요청: Z: 드라이브를 기준으로 작업
- 전역 기준: `Z:\Onedrive\Obsidian\HCS`
- fallback alias: `C:\Users\Administrator\OneDrive\Onedrive\Obsidian\HCS`
- TOOLS.md, MEMORY.md 업데이트 완료
- Z: 드라이브는 RaiDrive로 연결된 OneDrive → WSL `/mnt/z` 직접 접근 불가
- 실제 파일 조작은 C: alias 또는 Windows bridge로 우회 필요

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
