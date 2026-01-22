---
title: "BiasKG: Adversarial Knowledge Graphs to Induce Bias in Large Language Models"
---

# BiasKG: Adversarial Knowledge Graphs to Induce Bias in Large Language Models

[Github](https://github.com/VectorInstitute/biaskg)

Modern large language models (LLMs) have a significant amount of world knowledge, which enables strong performance in commonsense reasoning and knowledge-intensive tasks when harnessed properly. The language model can also learn social biases, which has a significant potential for societal harm. There have been many mitigation strategies proposed for LLM safety, but it is unclear how effective they are for eliminating social biases. 

In this work, we propose a new methodology for attacking language models with knowledge graph-augmented generation. We refactor natural language stereotypes into a knowledge graph, and use adversarial attacking strategies to induce biased responses from several open- and closed-source language models. We find our method increases bias in all models, even those trained with safety guardrails. This demonstrates the need for further research in AI safety, and further work in this new adversarial space.
## Significance
This project studied:
- How to create a knowledge graph from natural language phrases
- How to attack language models in a thorough, automated way
- How social bias can change depending on the input prompt

## Post mortem
I like the knowledge graph portion of this project, but I think the application to red-teaming is somewhat impractical now that the field is more mature. It was a good first attempt in a relatively new space, but red-teaming LLMs seems to be a fool's errand. There will always be a corner that is untested, and unlike traditional software, the cost of patching a hole is more than modifying some code - you would need to retrain the model, probably quite significantly.

In general, this project made me realize poorly trained LLMs still have all of the flaws of their predecessors. Minor changes in the input can result in significant changes to the output. Also, the temperature and other sampling parameters could change the result significantly. Recent models have removed temperature completely, probably for this reason. I realized that publishing on API-based models was also a fool's errand. We performed experiments with the same model (GPT-3.5) several months apart and received completely different results.

