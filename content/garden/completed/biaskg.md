---
title: "BiasKG: Adversarial Knowledge Graphs to Induce Bias in Large Language Models"
---

# BiasKG: Adversarial Knowledge Graphs to Induce Bias in Large Language Models

[Github](https://github.com/VectorInstitute/biaskg)

Modern large language models (LLMs) have a significant amount of world knowledge, which enables strong performance in commonsense reasoning and knowledge-intensive tasks when harnessed properly. The language model can also learn social biases, which has a significant potential for societal harm. There have been many mitigation strategies proposed for LLM safety, but it is unclear how effective they are for eliminating social biases. 

In this work, we propose a new methodology for attacking language models with knowledge graph-augmented generation. We refactor natural language stereotypes into a knowledge graph, and use adversarial attacking strategies to induce biased responses from several open- and closed-source language models. We find our method increases bias in all models, even those trained with safety guardrails. This demonstrates the need for further research in AI safety, and further work in this new adversarial space.
