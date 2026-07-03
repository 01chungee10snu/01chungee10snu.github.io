---
title: "2026-05-20; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-05-20
tags:
  - Obsidian일일회고
  - 일일회고
  - 기록관리
  - Hermes
  - 인프라-도구
  - AI-LLM
  - 데이터분석
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-05-20.md"
---

# 2026-05-20; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-05-20|2026-05-20 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-05-20에는 RISS 영어 키워드 잔여 수집 재실행, [[MEMORY.md]] 생성 + 위키링크 원칙 수립, [[현대제철]] 스토리라인 초안 발송, [[OneDrive]] WSL 마운트 구축 ([[rclone]])를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### RISS 영어 키워드 잔여 수집 재실행

### 배경
- 5/19 수집에서 WoS 22,828건 + RISS 7,610건 = 총 30,438건 수집 완료
- RISS 영어 키워드 2개가 타임아웃으로 중간에 끊김:
  - **Generative AI**: 18/54페이지 (1,785건)
  - **Generative Artificial Intelligence**: 12/29페이지 (1,180건)

### 수행 내용
1. 사용자가 나머지 수집 요청

### [[MEMORY.md]] 생성 + 위키링크 원칙 수립

- 장기 기억 파일 신규 생성, 핵심 작업 원칙·프로젝트·교훈 정리
- [[AGENTS.md]]에 "🕸️ Obsidian 위키링크 원칙" 섹션 추가
- 5월 누락 일지(05-12, 05-15, 05-19, 05-20) 전체 위키링크 보강
- [[일지-허브]]에 5월 일지 연결 추가

### [[현대제철]] 스토리라인 초안 발송

- [[한충석]] 책임매니저(`brienz311@hyundai-steel.com`)에게 이메일 발송
- Z: → PowerShell Copy-Item → C:\Temp → [[gog]] gmail send → 임시파일 삭제

### [[OneDrive]] WSL 마운트 구축 ([[rclone]])

- **문제**: built-in [[Admin]]에서 OneDrive 클라이언트 로그인 불가 → WSL에서 Z: (RaiDrive) 접근 불가
- **해결**: [[rclone]]으로 WSL에 OneDrive 직접 마운트
  - Windows rclone `authorize onedrive` → 브라우저 OAuth 인증
  - wslrelay 포트 53682 점유 → 기존 rclone 프로세스 kill 후 실행
  - `rclone mount onedrive: /mnt/onedrive --daemon --vfs-cache-mode full`
  - systemd 서비스 `rclone-onedrive` 등록 (부팅 시 자동 마운트)
- **결과**: WSL `/mnt/onedrive` 직접 접근, Windows는 기존 Z: (RaiDrive) 그대로
- [[TOOLS.md]] 업데이트 완료

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
