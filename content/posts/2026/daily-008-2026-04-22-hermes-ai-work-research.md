---
title: "2026-04-22; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-04-22
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
source: "Obsidian/Hermes/daily/2026-04-22.md"
---

# 2026-04-22; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-04-22|2026-04-22 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-04-22에는 Obsidian 볼트 이관 작업 (대규모), 전역 설정 업데이트, 최종 볼트 구조, 교훈를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### Obsidian 볼트 이관 작업 (대규모)

### Z: 드라이브 연결 확인
- `Z:\Onedrive\Obsidian\HCS` 볼트 구조 확인
- Z:는 RaiDrive로 연결된 OneDrive → WSL `/mnt/z` 직접 접근 불가
- C: alias 경로에서는 새 파일 읽기/쓰기 가능하나, 기존 OneDrive placeholder 파일은 I/O Error

### OneDrive 로그인 점검 (brienz311@gmail.com)
- built-in Administrator (SID-500) + UAC 비활성화 (EnableLUA=0) 환경
- OneDrive /reset + 재실행 시도 → 프로세스는 올라오나 계정 연결 안 됨

### 전역 설정 업데이트

- TOOLS.md: Obsidian 경로 → `C:\Obsidian\HCS` / `/mnt/c/Obsidian/HCS`
- MEMORY.md: 동일하게 업데이트, 이전 Z:/OneDrive 경로 제거

### 최종 볼트 구조

```
C:\Obsidian\HCS\
├── 충석.md              (포털)
├── HOME/
├── SNU👨🎓/
│   └── Zotero/ (9개 학업 문서)
├── WORK/
└── Openclaw/

### 교훈

- OneDrive placeholder 파일은 WSL에서 I/O Error → blocks=0으로 식별 가능
- RaiDrive Z:는 Obsidian 실사용에 너무 느림 → 로컬 SSD가 필수
- 심볼릭 링크로 OpenClaw 기억과 Obsidian을 통합하는 것이 가장 우아한 해결책
- PowerShell 스크립트는 UTF-8 BOM으로 저장해야 한국어 경로 처리 가능

### Obsidian Wiki 구축 및 적용 후속 정리 (2026-04-22 09:04 KST)

### obsidian-wiki 스킬 설치 및 설정
- GitHub의 `Ar9av/obsidian-wiki` 저장소를 검토하고 OpenClaw에 적용함.
- 설치 위치: `~/.openclaw/workspace/vendor/obsidian-wiki`
- 전역 스킬 등록 완료: `~/.openclaw/skills/`
- 설정 파일 생성: `~/.obsidian-wiki/config`
- 위키 대상 볼트 경로를 `C:\Obsidian\HCS` / `/mnt/c/Obsidian/HCS` 로 설정함.

### 볼트에 위키 계층 비파괴 적용

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
