---
title: "legalhatespeech"
---

# Towards legally enforceable hate speech detection for public forums

[Github](https://github.com/chufeiluo/legalhatespeech)
## Project Description
Hate speech causes widespread and deep-seated societal issues. Proper enforcement of hate speech laws is key for protecting groups of people against harmful and discriminatory language. However, determining what constitutes hate speech is a complex task that is highly open to subjective interpretations. Existing works do not align their systems with enforceable definitions of hate speech, which can make their outputs inconsistent with the goals of regulators. 

This research introduces a new perspective and task for enforceable hate speech detection centred around legal definitions, and a dataset annotated on violations of eleven possible definitions by legal experts. Given the challenge of identifying clear, legally enforceable instances of hate speech, we augment the dataset with expert-generated samples and an automatically mined challenge set. We experiment with grounding the model decision in these definitions using zero-shot and few-shot prompting. We then report results on several large language models (LLMs). 

With this task definition, automatic hate speech detection can be more closely aligned to enforceable laws, and hence assist in more rigorous enforcement of legal protections against harmful speech in public forums.
## Significance
This project studied:
- How to ground evaluations to be meaningful to another, specialized audience
- It was one of the first to benchmark LLMs - most of the experiments were completed January 2023 - against existing prompt tuning methods
- What is the source of ambiguity in other hate speech datasets

The paper also studied how to use self-training with silver labels to improve performance to match GPT-4 but with a much smaller model (RoBERTa-Large). This was only on a 3-way classification task and, as found in follow-up studies ([[sae-pd]]), there are some lexical features that allow LLMs to learn this classification label really well with few-shot prompting. 

## Post mortem
I still like this project. I think I'm still proud of it. I don't think the reasoning analysis is in-depth enough by today's standards, and my thoughts on model training vs. prompting flip-flop every so often, but it's been a while since I've had a paper compare model training to prompting. 
