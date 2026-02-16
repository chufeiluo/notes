---
title: "sae-pd"
---

# Towards Low-Resource Alignment to Diverse Perspectives with Sparse Feedback

[Github](https://github.com/chufeiluo/SAE-PD)

As language models have a greater impact on society, it is important to ensure they are aligned to a diverse range of perspectives and are able to reflect nuance in human values. However, the most popular training paradigms for modern language models often assume there is one optimal answer for every query, leading to generic responses and poor alignment. 

In this work, we aim to enhance pluralistic alignment of language models in a low-resource setting with two methods: pluralistic decoding and model steering. We empirically demonstrate that model steering offers consistent improvement over zero-shot and few-shot baselines with only 50 annotated samples. Our proposed methods decrease false positives in several high-stakes tasks such as hate speech detection and misinformation detection, and improves the distributional alignment to human values from different demographics. 

We hope our work highlights the importance of diversity and how language models can be adapted to consider nuanced perspectives.
## Significance
This project studies:
- How to do model alignment without model training
- Model steering on some abstract attribute ("feedback") instead of something concrete (e.g. hallucinations)
- How to combine multiple steering vectors at the decoding stage (works with or without model steering)

## Post-mortem?
To be honest, I'm not really satisfied with this project to the point that I hesitate to call this a post-mortem. I'm not leaving this project here, to be sure. I think the idea itself could be refined a little more. At its core I'm trying to ask: how can I use expert feedback efficiently? Can I emulate the behaviour of a model that has seen expert feedback, without needing an expert to give feedback on every single sample? I'm not sure how much that came across

I read a paper recently ([To believe or not to believe your LLM](https://arxiv.org/abs/2406.02543)) and it gave me new ideas for this paper. Basically, for any predicted token, you can measure the LLM's certainty in its prediction based on the change in probability over repetitions in the input context. If the probability fluctuates/drops when there are alternate answers in the context, this implies model is more easily influenced into changing its answer, so it's less sure. A very intuitive idea, and it works empirically.

In the context of my pluralistic decoding strategy, Pluralistic decoding, we perform 3 steps:
1. Take the difference in logit distribution between the base + steered logit
2. Measuring the entropy of the difference
3. Weighing the difference by the magnitude of entropy, add the displacement back to the base logit

Intuitively, the more the steered logit changed compared to the base, the more it would influence the final prediction logit. I was thinking this would reduce redundant information (i.e. we care about the logits that change significantly compared to the base, and we don't want them to get lost in an average of 6 other logits) but it also, in hindsight, "flattens" the prediction distribution when language models are more easily influenced. It's a kind of calibration in a way - if the model has a 0.9 chance of predicting "Yes" in the base vector, but a 0.9 chance of predicting "No" in one steering direction and a 0.9 chance of predicting "Unclear" in another steering direction, that should flatten out the distribution over all 3 choices. This reduces overconfidence, or places where a model was maybe too certain in the base instance. 

Maybe there is something there in reducing or detecting hallucinations? Or at least a measure of uncertainty in the model beyond logprobs. Uncertainty is a certain kind of reliability, since this can give some guidance on which samples require an actual human's attention.

Anyway - this paper had some interesting results, but I think it's a bit shallow.. I want to revisit this project if I get the time
