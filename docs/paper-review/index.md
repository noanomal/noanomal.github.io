---
title: 문헌리뷰
nav_order: 5
---

## 프롬프팅
### Chain of Density(CoT)
"From sparse to dense: GPT-4 summarization with chain of density prompting

## From sparse to dense: GPT-4 summarization with chain of density prompting
요약:
이 논문은 GPT-4가 요약을 할 때 “정보 밀도”를 점차 높이는 Chain of Density Prompting 기법을 제안합니다. 이 방법은 처음에는 간단한 요약을 만들고, 점점 더 많은 정보를 포함시키는 방식으로 요약을 확장합니다. 실험 결과, 정보가 풍부한 요약을 만들 때 이 방식이 효과적임을 보여줍니다.
## 논문 요약 프롬프팅 기술과 괄녀된 연구
"NapSS: Paragraph-level Medical Text Simplification via Narrative Prompting and Sentence-matching Summarization"
이 논문에서는 의료 문헌의 난해한 내용을 일반인이 이해하기 쉽게 단락 수준에서 단순화하는 방법을 제안합니다. 'NapSS'라는 두 단계 전략을 통해 먼저 요약을 생성한 후, 내러티브 프롬프트를 사용하여 원문의 흐름을 유지하면서 내용을 단순화합니다. 이 접근법은 기존 시퀀스-투-시퀀스 모델보다 어휘적 유사성에서 3~4%의 향상을 보였으며, SARI 점수에서도 추가적인 1.1%의 개선을 달성했습니다.

"Curriculum Prompt Learning with Self-Training for Abstractive Dialogue Summarization"
이 연구는 대화 요약에서 프롬프트 학습과 자기 학습을 결합한 새로운 커리큘럼 학습 방법을 제안합니다. 프롬프트를 점진적으로 학습하여 모델의 대화 이해 및 생성 능력을 향상시키며, 라벨이 없는 데이터를 자기 학습으로 활용하여 라벨된 데이터에 대한 의존도를 낮춥니다. 이 방법은 AMI와 ICSI 데이터셋에서 기존 모델보다 우수한 성능을 보였습니다.

"Latent Prompt Tuning for Text Summarization"
이 논문에서는 텍스트 요약에서 다양한 제어 신호(예: 길이, 키워드 등)를 활용하여 요약의 특성을 조절하는 방법을 탐구합니다. 제안된 'Lotus' 모델은 훈련 시 대조 학습 목표를 통해 잠재 프롬프트 표현을 학습하며, 이를 통해 제어 신호 없이도 기존 요약 모델보다 향상된 성능을 보여줍니다.

"The Effect of Prompt Types on Text Summarization Performance With Large Language Models"
이 연구는 대형 언어 모델에서 다양한 프롬프트 유형이 텍스트 요약 성능에 미치는 영향을 조사합니다. 세 가지 프롬프트 유형(단순 지시, 몇 가지 예시 제공, 역할 부여)을 비교하여, 프롬프트의 설계가 요약 품질에 어떻게 영향을 주는지 분석합니다.

"Optimizing Prompt Engineering for Automated Text Summarization of Student Reflections: A Comparative Study Using GPT-4 LLM"
이 연구는 학생들의 반성문을 자동으로 요약하기 위해 GPT-4를 활용한 프롬프트 엔지니어링 최적화 방법을 비교 분석합니다. 다양한 수준의 프롬프트를 사용하여 생성된 요약을 평가하고, 프롬프트에 상세한 컨텍스트를 제공하는 것이 요약 품질 향상에 도움이 됨을 발견했습니다.



논문 제목: Summqa at mediqa-chat 2023: In-context learning with GPT-4 for medical summarization
요약:
이 논문은 GPT-4를 활용해 의료 문서 요약을 수행한 결과를 소개합니다. 특히 별도의 fine-tuning 없이, In-context learning만으로도 뛰어난 성능을 보여주었으며, 다양한 예시와 지침을 통해 성능을 향상시켰습니다.

논문 제목: Can GPT models follow human summarization guidelines?
요약:
이 논문은 ChatGPT와 GPT-4가 사람이 만든 요약 지침을 얼마나 잘 따를 수 있는지를 평가합니다. 주로 대화형 텍스트 요약에 초점을 맞췄으며, 모델이 전반적으로 성능은 뛰어나지만, 세부적인 지침을 완전히 따르지는 못하는 경우가 많음을 보고합니다.

논문 제목: Leveraging GPT-4 for food effect summarization...
요약:
이 논문은 약물-음식 상호작용에 대한 정보를 요약하기 위해 GPT-4를 활용합니다. 반복적 프롬프트(Iterative Prompting)를 사용해, 제품별 가이드라인 생성을 돕는 방식입니다. 모델은 복잡한 생의학 정보를 요약하는 데 적합함을 보여줍니다.

논문 제목: Source code summarization in the era of large language models
요약:
이 논문은 LLM을 활용한 소스코드 요약에 관한 연구입니다. GPT-계열 모델들이 개발자 수준의 요약을 생성할 수 있음을 보이며, 기존 모델 대비 품질이 크게 향상되었다고 보고합니다. 단, 코드 구조 이해에는 여전히 한계가 있습니다.

논문 제목: Clinical text summarization: adapting large language models can outperform human experts
요약:
의료 기록 요약에서 LLM을 fine-tuning하거나 prompt를 조정하면 인간 전문가보다 나은 성능을 낼 수 있음을 보입니다. 특히, 복잡한 임상 메모를 정리하는 데 있어 LLM의 잠재력을 강조합니다.

논문 제목: SummIt: Iterative Text Summarization via ChatGPT
요약:
기존의 단일 단계 요약 방식의 한계를 극복하기 위해 SummIt이라는 프레임워크를 제안합니다. 이 프레임워크는 대형 언어 모델인 ChatGPT를 활용하여 요약문을 생성한 후, 자체 평가와 피드백을 통해 반복적으로 수정하는 방식을 채택합니다. 이러한 접근 방식은 사람이 초안을 작성하고 수정하는 과정과 유사하며, 요약문의 정확성과 충실도를 향상시키는 데 도움이 됩니다.