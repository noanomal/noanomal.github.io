---
title: Chain of Density(CoD)
parent: 문헌리뷰
nav_order: 2
---

## Chain of Density(CoD)
### CoD 란 ?
CoD는 문서 요약을 위해 개발된 프롬프트 기법으로, 요약문의 **정보 밀도(entity density)** 를 점차 높이는 기법입니다. 본 논문에서는 요약문의 길이는 그대로 유지하면서, 총 2단계를 5번에 걸쳐 반복적으로 요약문을 생성하고, 그 과정에서 점점 더 많은 핵심 정보를 담도록 유도하는 방식을 제안합니다.

### 정보 밀도(entity density)란?
본 논문에서는 정보 밀도를 직접적으로 설명하기 보다 정보 밀도가 가지는 특징 5가지를 아래와 같이 설명합니다.
- Relevant: 이야기의 핵심과 관련 있는 정보
- Specific: 짧고 구체적이으로 표현(5단어 이내)
- Novel: 이전 용약에 없던 새 정보
- Faithful: 본문에 실제로 등장한 정보
- Anuwhere: 본문 어디에든 있기만 하면됨

### 프롬프트 예시
```bash
Article: {{ARTICLE}}

You will generate increasingly concise, entity-dense summaries of the above Article.

Repeat the following 2 steps 5 times.

Step 1. Identify 1-3 informative Entities (";" delimited) from the Article which are missing from the previously generated summary.
Step 2. Write a new, denser summary of identical length which covers every entity and detail from the previous summary plus the Missing Entities.

A Missing Entity is:
 - Relevant: to the main story.
 - Specific: descriptive yet concise (5 words or fewer).
 - Novel: not in the previous summary.
 - Faithful: present in the Article.
 - Anywhere: located anywhere in the Article.

Guidelines:
 - The first summary should be long (4–5 sentences, ~80 words) yet highly non-specific, containing little information beyond the entities marked as missing. Use overly verbose language and fillers (e.g., "this article discusses") to reach ~80 words.
 - Make every word count: re-write the previous summary to improve flow and make space for additional entities.
 - Make space with fusion, compression, and removal of uninformative phrases like "the article discusses".
 - The summaries should become highly dense and concise yet self-contained, e.g., easily understood without the Article.
 - Missing entities can appear anywhere in the new summary.
 - Never drop entities from the previous summary. If space cannot be made, add fewer new entities.

Remember, use the exact same number of words for each summary.

Answer in JSON. The JSON should be a list (length 5) of dictionaries whose keys are "Missing_Entities" and "Denser_Summary".
```
## 평가 방법
본 논문에서 제안하는 논문 저자가 요약문이 얼마나 잘 요약되었는 평가하는 방법과, GPT4 가 원문과 요약문을 비교하여 얼마나 잘 요약되었는지를 평가하는 방법 두가지를 제안하였스며, 후자를 위한 프롬프트 예시는 아래와 같다.

```bash
Article: {{Article}}
Summary: {{Summary}}
Please rate the summary (1 = worst to 5 = best) with respect to {{Dimension}}.
{{Definition}}

Below, we present the definitions provided for each quality metric.

• Informative: An informative summary captures the important information in the article and presents it accurately and concisely.
• Quality: A high quality summary is comprehensible and understandable.
• Coherence: A coherent summary is well-structured and well-organized.
• Attributable: Is all the information in the summary fully attributable to the Article?
• Overall Preference: A good summary should convey the main ideas in the Article in a concise, logical, and coherent fashion.
```

- 정보성(Informative): 정보성 요약은 기사에서 중요한 정보를 포착하여 정확하고 간결하게 제시합니다.
- 품질(Quality): 고품질 요약은 이해하기 쉽고 명확해야 합니다.
- 일관성(Coherence): 일관성 있는 요약은 구조가 잘 잡혀 있고 조직적으로 정리되어 있습니다.
- 출처 명확성(Attributable): 요약에 포함된 모든 정보가 기사로부터 명확히 출처를 알 수 있어야 합니다.
- 종합적 선호도(Overall Preference): 좋은 요약은 기사의 주요 아이디어를 간결하고 논리적이며 일관성 있게 전달해야 합니다.

## 평가 결과