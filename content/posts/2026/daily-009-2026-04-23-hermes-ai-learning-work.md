---
title: "2026-04-23; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다"
date: 2026-04-23
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
category: "Obsidian 일일 회고"
source: "Obsidian/Hermes/daily/2026-04-23.md"
---

# 2026-04-23; 나는 Hermes 기록을 정리하며 지식 흐름을 남겼다

## 연결

- [[Hermes/daily/2026-04-23|2026-04-23 일지]]
- [[Hermes/daily/일지-허브|일지-허브]]
- [[categories/obsidian-daily-retrospective|Obsidian 일일 회고]]

## 오늘의 회고

2026-04-23에는 gog 관련 수행 내역 정리, ChatGPT/OpenAI 로그인 전환 메모 (10:38 KST), 후속를 중심으로 하루의 기록을 남겼다. 흩어진 실행과 판단을 나중에 다시 읽을 수 있는 단위로 묶어두는 데 초점을 두었다.

## 기록에서 건진 것

### gog 관련 수행 내역 정리

### 초기 구축 및 학습 이력 회고
- 2026-04-15에 `gog` CLI(`v0.9.0`) 설치/동작 상태를 점검하고, `brienz311@gmail.com` 기준 Google OAuth 설정을 완료함.
- Google Cloud Console에서 Desktop OAuth client 생성, Test users 추가, Windows에서 받은 JSON의 WSL 경로 변환, 브라우저 승인 흐름까지 정리함.
- `gog` 설정 교훈은 `.learnings/gog-oauth-setup-lessons.md` 와 `.learnings/gog-keyring-wrapper.md`에 기록했고, 재사용을 위해 `scripts/gog-call.sh` 래퍼를 둠.
- OAuth 성공 후 `Calendar API` 및 `Gmail API`를 별도로 활성화해야 실제 명령이 정상 동작한다는 점을 확인함.
- `gog:daily-calendar-brief` cron job을 등록해 매일 07:00, 13:00 한국어 캘린더 브리핑을 수행하도록 구성했음.

### 2026-04-22 ~ 2026-04-23 추가 정리

### ChatGPT/OpenAI 로그인 전환 메모 (10:38 KST)

- 모델 인증 로그인 아이디를 바꾼 뒤 아래 메시지가 나타남:
  - `Config overwrite: /home/brienz311/.openclaw/openclaw.json`
  - `sha256 <old> -> <new>`
  - `backup=/home/brienz311/.openclaw/openclaw.json.bak`
  - `Updated ~/.openclaw/openclaw.json`
- 의미: 오류가 아니라 OpenClaw 설정 파일이 새 인증/모델 선택 값으로 실제 갱신되었다는 뜻으로 해석됨.
- 이전 설정은 `openclaw.json.bak`로 백업되므로, 필요 시 이전 상태 복구 기준점으로 삼을 수 있음.
- 사용자는 앞으로 ChatGPT/OpenAI 로그인 아이디를 여러 개 사용하고, 필요할 때 전환해 쓰는 운영을 원함.

### 후속

- [ ] `gog:daily-calendar-brief`가 `default`/`calandrem` 중 어느 텔레그램 계정으로 나갈지 최종 정책 확정
- [ ] 필요 시 `gog` 관련 운영 규칙을 별도 wiki 문서로 승격
- [ ] ChatGPT/OpenAI 로그인 다계정 전환 시 계정별 용도 메모 규칙 정리

## 그래프뷰 관계

- [[일일회고]]는 [[기록관리]]와 연결된다. 하루 단위의 기록은 나중에 주간·월간 회고로 다시 묶일 수 있다.
- [[자기돌봄]]은 단발성 판단보다 반복 관찰을 통해 더 선명해진다.
- [[Obsidian]]의 원자료를 [[Quartz]] 블로그 글로 전환하면서, 사적인 기록은 공개 가능한 해석으로 한 번 더 정제된다.
