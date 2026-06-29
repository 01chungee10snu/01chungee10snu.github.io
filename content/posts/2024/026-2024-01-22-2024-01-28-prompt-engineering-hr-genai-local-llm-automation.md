---
title: "026_2024년 1월 4주차; 나는 프롬프트 엔지니어링과 HR 생성형 AI 자동화를 실험했다"
date: 2024-01-28
category: "ChatGPT 대화이력 회고"
series: "ChatGPT 대화이력 주간 회고"
week: "2024-01-22~2024-01-28"
tags:
  - ChatGPT대화이력
  - 프롬프트엔지니어링
  - ExcelVBA
  - ChatGPTAPI
  - ActionPlan
  - 리더십개발
  - 로컬LLM
  - HuggingFace
  - KoR-Orca-Platypus
  - HR
  - 생성형AI
  - 디지털트랜스포메이션
  - PowerAutomate
  - 문서분석
  - 이미지생성
---

# 026_2024년 1월 4주차; 나는 프롬프트 엔지니어링과 HR 생성형 AI 자동화를 실험했다

## 연결
- [[ChatGPT 대화이력]]
- [[프롬프트 엔지니어링]]
- [[Zero-shot Learning]]
- [[One-shot Learning]]
- [[Few-shot Learning]]
- [[Chain of Thought]]
- [[Excel VBA]]
- [[ChatGPT API]]
- [[OpenAI API]]
- [[max_tokens]]
- [[토큰 제한]]
- [[Action Plan]]
- [[리더십 개발]]
- [[팀장 교육]]
- [[Python]]
- [[CSV]]
- [[로컬 LLM]]
- [[Hugging Face]]
- [[KoR-Orca-Platypus]]
- [[Transformers]]
- [[CUDA]]
- [[GPU]]
- [[NVIDIA RTX A2000]]
- [[HR]]
- [[생성형 AI]]
- [[디지털 트랜스포메이션]]
- [[조직운영]]
- [[인력운영]]
- [[문서분석]]
- [[이미지 생성]]
- [[현대제철]]

2024년 1월 4주차의 [[ChatGPT 대화이력]]은 생성형 AI를 실무 도구로 만들기 위한 실험이 가장 강하게 드러난 주간이었다. 나는 [[프롬프트 엔지니어링]]의 원리를 묻고, [[Excel VBA]]에서 [[ChatGPT API]]를 호출하는 코드를 고치고, 팀장 교육의 [[Action Plan]]에 대한 개인별 피드백을 자동 생성하려 했다. 동시에 PC에 [[로컬 LLM]]을 설치하려고 했고, [[HR]] 조직이 [[생성형 AI]]로 어떻게 바뀔 수 있는지 토론과 브레인스토밍을 반복했다.

첫 출발은 프롬프트 자체였다. 나는 ChatGPT를 단순 답변기가 아니라 프롬프트 설계 전문가로 세우고자 했다.

> “적절한 프롬프트 엔지니어링 기법을 활용하고 싶어.”

> “너는 프롬프트 엔지니어링 분야의 최고전문가의 입장에서 나에게 가장 완벽한 조언을 전해줄 수 있어.”

며칠 뒤에는 [[Zero-shot Learning]], [[One-shot Learning]], [[Few-shot Learning]], [[Chain of Thought]]를 프롬프트 엔지니어링 설명 개념으로 쓰고자 했다.

> “prompt engineering을 설명하기 위한 개념으로 zero shot learning, one shot learning, few shot learning, chain of thought를 사용하고 싶어.”

> “해당 개념에 대한 설명과 예시, 각 결과물의 차이를 표로 정리해서 알려줘.”

이 질문은 내가 생성형 AI를 개인적으로 쓰는 수준을 넘어, 다른 사람에게 설명하고 교육할 수 있는 개념 체계를 만들려 했음을 보여준다.

두 번째 흐름은 [[Excel VBA]]와 [[ChatGPT API]]의 결합이었다. 나는 Excel에서 바로 GPT를 호출하는 함수를 만들고 있었다.

> “나는 엑셀 VBA에서 chatGPT API를 활용한 함수를 만들고 있어. 아래 함수를 검토해줘.”

이 대화에는 실제 코드와 오류가 이어졌다. 공개 글에서는 API 키를 제외하지만, 당시의 핵심은 함수 구조를 Chat Completions API에 맞추고, 응답 파싱과 토큰 설정을 고치는 일이었다.

> “프롬프트를 설계해서 함수를 실행시켰는데 #Error! : 0 is less than the minimum of 1 - 'max_tokens' 라는 오류가 나타났어 해결되도록 도와줄래?”

> “#Error! : 'role' is a required property - 'messages.0' 이런 오류메시지도 나타났어 도와줄래”

> “This model's maximum context length is 16385 tokens. However, you requested 16527 tokens … 해결할 수 있는 방안을 알려줄래?”

> “실행을 하니까 아무메시지도 나오지않아. 도와줘.”

> “You exceeded your current quota, please check your plan and billing details … 이 오류를 해결하도록 도와줘.”

이 오류들은 API 자동화의 실제 장벽이었다. [[max_tokens]]가 0이면 요청이 실패하고, chat 모델은 `messages` 배열 안에 `role`과 `content`가 있어야 하며, 모델의 컨텍스트 한도를 초과하면 짧은 질문도 실패할 수 있다. 특히 짧은 프롬프트인데도 토큰 초과가 난 상황은 코드에서 기본 `Max_Tokens`를 모델 최대치로 과하게 잡은 것이 문제였을 가능성이 컸다.

나는 결국 Excel에서 쓸 수 있는 VBA 코드를 다시 요청했다.

> “chatGPT API를 통해 엑셀 함수에서 사용할 수 있는 VBA 코드를 부탁해”

세 번째 흐름은 팀장 교육 [[Action Plan]] 피드백 자동화였다. 나는 대기업 사무직 팀장 교육 결과로 수립된 액션플랜에 대해 피드백 예시를 만들고자 했다.

> “너의 역할 : 리더십 개발 전문가”

> “대기업 사무직 팀장들을 대상으로 교육한 결과, 팀장들이 본인의 리더십 개선을 위한 Action Plan을 수립할 예정임.”

> “Action Plan의 예시문장을 생성해줘.”

그다음에는 CSV 파일을 Python으로 읽고, [[ChatGPT API]]를 이용해 개인별 피드백을 생성한 뒤 새 열에 붙이는 구조를 만들려 했다.

> “나는 Action Plan이 기록된 csv 파일을 Python에 입력시켜서 chatGPT API를 활용해서 Action Plan에 대한 피드백을 생성한 이후 기존 csv 파일의 새로운 열에 추가하고 싶어.”

> “나는 로컬에서 직접 수행해보고 싶어. csv 파일을 등록하는 명령어를 알려줘.”

실행 과정에서는 Windows 경로의 백슬래시 때문에 `unicodeescape` 오류가 발생했다.

> “SyntaxError: (unicode error) 'unicodeescape' codec can't decode bytes in position 2-3: truncated \\UXXXXXXXX escape”

이후 나는 API 호출 함수, 프롬프트, 결측치 제거, 첫 번째 행 테스트, 소요시간 측정, 15초 간격 반복 실행까지 단계적으로 요청했다.

> “개인별 Action Plan에 대한 내용을 반영해서 개별적인 피드백을 생성하고 csv 파일의 새로운 열에 내용을 추가하고 싶어 도와줘.”

> “전체 Action Plan 중 첫번재 행에 대한 피드백만 생성해보고, 소요시간을 알려주는 코드를 생성해줘.”

> “선언적인 조언이 아니라 실제 행동으로 옮길 수 있는 가이드를 제시해주어야해.”

> “15초 간격으로 1개 행씩 실행시키고 싶어 나의 필요사항을 반영한 코드를 짜줘.”

이 흐름은 [[리더십 개발]]이 자동화와 만난 장면이었다. 교육생의 [[Action Plan]]을 일괄 처리하되, 각자에게 맞춘 실천 피드백을 생성하려 했다. 나는 이 자동화가 너무 빠르게 API 한도를 초과하지 않도록 시간 간격까지 고려했다.

네 번째 흐름은 [[로컬 LLM]] 설치였다. 나는 PC에서 직접 LLM 모델을 돌리고 싶어 했다.

> “나는 PC에 LLM 모델을 설치해서 사용하고 싶어. 앞으로 내가 물어보는 질문에만 대답해줘.”

대상 모델은 [[Hugging Face]]의 KoR-Orca-Platypus 계열이었고, Windows 환경에서 SSL 인증서, 패키지 버전, 오프로딩, CUDA, 디스크 용량 문제가 이어졌다.

> “fatal: unable to access … SSL certificate problem: self signed certificate in certificate chain 이 것에 대해서 조치해줘”

> “tokenizers>=0.11.1,!=0.11.3,<0.14 is required … 이 오류를 해결해줘”

> “Please provide an `offload_folder` for them.”

> “You can't move a model that has some modules offloaded to cpu or disk. 이런 오류가 나타났어 도와줄래?”

> “No space left on device”

마지막에는 보유 GPU 기준으로 가능한 모델 규모를 물었다.

> “현재 보유한 GPU에서 가동시킬 수 있는 로컬LLM 모델을 찾는 방법을 알려줘 내가 보유한 GPU는 NVIDIA RTX A2000 laptop 이야, VRAM은 4GB 어느 정도 수준의 LLM을 가동시킬 수 있어ㅛ/”

> “현재 보유한 GPU로 13B 크기의 LLM을 가동시키는 것은 가능할까?”

이 질문들은 내가 [[OpenAI API]]만 쓰는 대신, [[로컬 LLM]]을 직접 설치해 통제 가능한 AI 환경을 만들려 했다는 점을 보여준다. 동시에 13B 모델과 4GB VRAM의 현실적인 한계도 마주했다.

다섯 번째 흐름은 [[HR]]와 [[생성형 AI]]의 전략적 결합이었다. 나는 철강 대기업 HR 조직의 변화 가능성을 큰 틀에서 논의하고자 했다.

> “나는 앞으로 chatGPT4를 이용해서 대한민국 철강대기업의 HR 조직의 업무수행, 더 나아가 인력/조직운영을 어떻게 변화시킬지에 대해 논의할거야.”

> “조직운영과 인적자원관리와 육성에 대한 심도있는 논의를 해줘야해.”

처음에는 HR의 영역부터 물었다.

> “우선 HR의 영역이 무엇인지에 대해서부터 논의해보자.”

이후 질문은 생성형 AI 기반 HR 디지털 전환으로 옮겨갔다.

> “나는 생성형 AI 기술을 활용해서 기업의 HR 부문의 디지털 트랜스포메이션을 추진하고 싶어. 적절한 방향을 알려줘.”

나는 자동화가 생산성 향상을 넘어 조직 구조와 인력 운영에 영향을 줄 것이라고 보았다.

> “AI 기술을 활용하면 업무 생산성 대신 업무 자동화가 이루어질 텐데, 그렇게 되면 필연적으로 인간의 노동력이 부족해 필요 없게 될 것이고, 그에 따라서 인력 구조 대신 조직 구조에 큰 변화가 일어날 수 있을 것 같습니다.”

글로벌 컨설팅 보고서, 학술논문, 기업 사례도 요구했다.

> “생성형 AI의 등장과 HR 업무변화, 기업인력/조직운영 변화에 대한 Insight를 보여주는 글로벌 최고수준의 컨설팅 회사의 보고서, 최고권위 학술지에 게재된 연구논문, 글로벌 탑 티어 회사의 사례를 종합적으로 찾아서 알려주고 APA Style로 제시해줘”

또한 자동화가 인력감축으로만 쓰이지 않도록 하는 방안과 잉여인력의 재배치, 신규 직무, 신규 조직까지 물었다.

> “자동화가 인력감축의 용도로만 사용되지 않기 위한 방안은?”

> “잉여인력들을 어떻게 활용해야하는지, 어떠한 직무를 창조해야 하는지, 어떠한 조직을 구성해서 이끌어가야 하는지 육하원칙을 기반으로 설명해줘”

마지막에는 극단적인 입장의 가상 토론자와 중재자를 세워 새로운 인사전략을 도출하려 했다.

> “가상의 토론자 2명이 각자 극단적인 입장에서 인공지능 기술의 도입에 따른 기업 HR 전략변화와 그 영향에 대한 토론문을 생성해주고…”

> “중재자는 모든 토론을 종합하면서 어느 누구도 생각하지 못했던 인사이트를 도출할 수 있도록 해봐.”

이 대화는 [[생성형 AI]]가 HR에 들어올 때 생기는 긴장을 보여준다. 자동화는 효율을 만들지만, 동시에 인간 노동과 조직 구조의 재정의를 요구한다. 나는 이 긴장을 회피하지 않고 토론 형식으로 밀어붙였다.

여섯 번째 흐름은 이미지와 문서 분석이었다. 나는 [[생성형 AI]]와 기업 HR의 결합을 시각적으로 표현하려 했다.

> “기업의 HR과 Generative AI 기술의 결합을 보여주는 그림을 알려줘”

> “방금 알려준 이미지는 너무 실제적이야 기하학적이고 추상적이고 에테리얼하게 표현해줘”

> “이미지의 사이즈는 가로 16: 세로 9로 해줘”

> “Transformer에서 사용되는 Attention machanism을 설명할 수 있는 이미지를 생성해줘”

문서 분석에서는 PDF 자료를 바탕으로 특정 회사 전망을 묻기도 했다.

> “앞서 알려준 모든 내용을 한글로 번역해줘.”

> “여기에서 언급된 회사의 이름은 ‘현대제철’이야. 분석보고서의 내용을 토대로 회사의 전망에 대한 의견을 전달해줘.”

이 흐름은 내가 AI를 텍스트 생성뿐 아니라 이미지 구상, 보고서 번역, 기업 분석 보조에도 쓰고 있었음을 보여준다.

026주차의 대화들은 기술 오류와 전략 질문이 한꺼번에 섞여 있었다. 하지만 방향은 분명했다. 나는 [[프롬프트 엔지니어링]]을 익혀 더 좋은 질문을 만들고, [[Excel VBA]]와 [[Python]]으로 실제 업무를 자동화하며, [[로컬 LLM]]으로 실행 환경을 넓히고, [[HR]]의 미래를 [[생성형 AI]] 관점에서 재설계하려 했다.

## 이 주의 직접인용

- “적절한 프롬프트 엔지니어링 기법을 활용하고 싶어.”
- “prompt engineering을 설명하기 위한 개념으로 zero shot learning, one shot learning, few shot learning, chain of thought를 사용하고 싶어.”
- “나는 엑셀 VBA에서 chatGPT API를 활용한 함수를 만들고 있어.”
- “#Error! : 0 is less than the minimum of 1 - 'max_tokens' 라는 오류가 나타났어 해결되도록 도와줄래?”
- “#Error! : 'role' is a required property - 'messages.0' 이런 오류메시지도 나타났어 도와줄래”
- “chatGPT API를 통해 엑셀 함수에서 사용할 수 있는 VBA 코드를 부탁해”
- “나는 Action Plan이 기록된 csv 파일을 Python에 입력시켜서 chatGPT API를 활용해서 Action Plan에 대한 피드백을 생성한 이후 기존 csv 파일의 새로운 열에 추가하고 싶어.”
- “선언적인 조언이 아니라 실제 행동으로 옮길 수 있는 가이드를 제시해주어야해.”
- “15초 간격으로 1개 행씩 실행시키고 싶어 나의 필요사항을 반영한 코드를 짜줘.”
- “나는 PC에 LLM 모델을 설치해서 사용하고 싶어.”
- “현재 보유한 GPU는 NVIDIA RTX A2000 laptop 이야, VRAM은 4GB 어느 정도 수준의 LLM을 가동시킬 수 있어ㅛ/”
- “현재 보유한 GPU로 13B 크기의 LLM을 가동시키는 것은 가능할까?”
- “나는 생성형 AI 기술을 활용해서 기업의 HR 부문의 디지털 트랜스포메이션을 추진하고 싶어.”
- “자동화가 인력감축의 용도로만 사용되지 않기 위한 방안은?”
- “기업의 HR과 Generative AI 기술의 결합을 보여주는 그림을 알려줘”
- “Transformer에서 사용되는 Attention machanism을 설명할 수 있는 이미지를 생성해줘”

## 그래프뷰 관계

- [[프롬프트 엔지니어링]] → [[Zero-shot Learning]]: 프롬프트 교육을 위한 기본 개념으로 사용했다.
- [[프롬프트 엔지니어링]] → [[Chain of Thought]]: 단계적 사고를 유도하는 프롬프트 전략을 설명하려 했다.
- [[Excel VBA]] → [[ChatGPT API]]: Excel 함수에서 GPT 응답을 직접 호출하는 자동화를 실험했다.
- [[ChatGPT API]] → [[max_tokens]]: 토큰 설정 오류가 API 호출 실패의 원인이 되었다.
- [[ChatGPT API]] → [[OpenAI API]]: chat completions 엔드포인트와 요청 형식에 맞춰 코드를 수정했다.
- [[Action Plan]] → [[리더십 개발]]: 팀장 교육 후 개인별 실천계획에 피드백을 생성하려 했다.
- [[Action Plan]] → [[Python]]: CSV를 불러와 행별 피드백을 생성하고 새 열에 저장하려 했다.
- [[Python]] → [[CSV]]: 교육생 데이터를 처리하고 결과를 파일로 내보내는 실행 환경이었다.
- [[로컬 LLM]] → [[Hugging Face]]: PC에서 모델을 직접 내려받아 실행하려 했다.
- [[로컬 LLM]] → [[NVIDIA RTX A2000]]: 4GB VRAM 기준으로 가능한 모델 크기를 검토했다.
- [[Transformers]] → [[CUDA]]: 모델 실행 과정에서 패키지 버전과 GPU 환경 문제가 발생했다.
- [[HR]] → [[생성형 AI]]: HR 업무와 조직운영을 생성형 AI 관점에서 재설계하려 했다.
- [[생성형 AI]] → [[디지털 트랜스포메이션]]: HR 부문의 DX 추진 방향을 탐색했다.
- [[생성형 AI]] → [[조직운영]]: 자동화 이후 인력구조와 조직구조의 변화를 검토했다.
- [[이미지 생성]] → [[HR]]: HR과 생성형 AI의 결합을 시각적으로 표현하려 했다.
- [[문서분석]] → [[현대제철]]: PDF 분석 내용을 바탕으로 회사 전망 의견을 생성하려 했다.
