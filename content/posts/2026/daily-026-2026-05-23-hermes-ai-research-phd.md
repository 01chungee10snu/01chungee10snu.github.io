---
title: "2026-05-23; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-05-23
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
source: "Obsidian/Hermes/daily/2026-05-23.md"
---

# 2026-05-23; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-05-23|2026-05-23 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-05-23에는 로그를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### 로그

- 08:54 [[yonggangi-cursor-pack]] v9 생성. 사용자 요청에 따라 Link 커서의 손가락 끝 원형 캡을 제거하고, `YonggangiCursorPack_GPTImaGen_InvisibleHotspot_v9` 에셋/설치 패키지를 재빌드했다. Link 핫스팟은 `(50, 18)`로 유지했고 `.cur` 16개, `.ani` 2개 검증이 통과했다.
- 09:18 [[yonggangi-cursor-pack]] Windows 적용 오류 수정. `Working.ani`/`BusyTransform.ani`가 Windows `LoadCursorFromFile`에서 실패하는 원인은 `.ani` 프레임에 128px 커서 엔트리가 포함된 것이었다. 애니메이션은 32/48/64/96px만 포함하도록 재생성하고 `%LOCALAPPDATA%` 설치본과 바탕화면 패키지/ZIP을 갱신했다. 패키지 루트에 `제작과정.txt`를 추가했고, [[Hermes/wiki/references/windows-cursor-pack]]에도 128px `.ani` 금지 교훈을 기록했다.
- 09:28 [[yonggangi-cursor-pack]] 배포 브랜딩 정리. 최종 배포 폴더를 `용강이 마우스 커서세트`로 바꾸고, 설치 시 Windows 구성표명이 `현대제철 용강이 마우스 커서세트`로 등록되도록 `install.ps1`을 수정했다. `README.txt`와 `제작과정.txt`는 `(필독) 설치방법과 제작과정.txt`로 통합했고 Windows 11 원상복구 경로를 추가했다.
- 09:43 [[yonggangi-cursor-pack]] 프로젝트 통합 완료. 바탕화면 `C:\Users\Administrator\OneDrive\Desktop\MouseCursor`와 OpenClaw `outputs/yonggangi-*` 산출물을 `C:\Github\MouseCursor`로 모았다. 최종 배포본은 `dist/current`, 이전 배포/바탕화면 산출물은 `dist/archive`, 재사용 이미지 에셋은 `assets`, 생성 이력은 `workspace-outputs`, 빌드 스크립트는 `scripts`, 제작 노트는 `docs/pipeline-notes`에 배치했다. 로컬 Git 저장소로 초기화하고 브랜치를 `main`으로 설정했다.
- 09:48 [[yonggangi-cursor-pack]] 프로젝트 경량화. 사용자가 중간 산출물은 없어도 된다고 정정해서 `C:\Github\MouseCursor`의 `workspace-outputs`와 `dist/archive` 대용량 내용을 휴지통 처리했다. 최종 배포본, 최종 소스 PNG, 스크립트, 문서만 남겨 프로젝트 크기를 약 480MB에서 17MB로 줄였다.
- 09:58 [[yonggangi-cursor-pack]] 배포 메일 발송. `C:\Github\MouseCursor\dist\current\용강이 마우스 커서세트.zip`을 `brienz311@hyundai-steel.com`으로 [[gog]] Gmail CLI를 통해 발송했다. 보낸 계정은 `brienz311@gmail.com`, 메시지 ID는 `19e5256a62a76e74`, Gmail `SENT` 라벨과 `multipart/mixed` 메타데이터로 발송 및 첨부 포함을 확인했다.
- 10:08 [[yonggangi-cursor-pack]] Gmail 첨부 차단 대응. 기존 ZIP은 `.cmd/.ps1` 자동설치 스크립트 포함으로 Google 보안 정책에 의해 반송됐다. 실행 스크립트와 `.inf`를 제외한 `용강이 마우스 커서세트_메일발송용.zip`을 만들고 수동 설치 안내문을 추가해 재발송했다. 새 메시지 ID는 `19e525e4697ce138`, `SENT` 및 `multipart/mixed` 확인 완료, 관련 반송 메일은 현재 없음.
- 09:06 [[ihateppt]] 프로젝트 상태 확인. `examples/reportspec_native_demo.json`를 `report_pipeline evaluate`로 검증했고 `accepted: true`, report/layout/visual quality 모두 100/100, gate failure 0건이었다. GUI 테스트는 WSL의 `tkinter` 부재로 수집 실패하므로 제외했고, 비-GUI pytest는 182 passed.

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
