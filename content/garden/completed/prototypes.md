---
title: "prototypes"
---

# Prototype-based Interpretability for Legal Citation Prediction

[Github](https://github.com/chufeiluo/prototype-lcp)

## Project Description
Deep learning has made significant progress in the past decade, and demonstrates potential to solve problems with extensive social impact. In high-stakes decision making areas such as law, experts often require interpretability for automatic systems to be utilized in practical settings. 

In this work, we attempt to address these requirements applied to the important problem of legal citation prediction (LCP). We design the task with parallels to the thought-process of lawyers, i.e., with reference to both precedents and legislative provisions. After initial experimental results, we refine the target citation predictions with the feedback of legal experts. Additionally, we introduce a prototype architecture to add interpretability, achieving strong performance while adhering to decision parameters used by lawyers. 

Our study builds on and leverages the state-of-the-art language processing models for law, while addressing vital considerations for high-stakes tasks with practical societal impact.

## Significance
This project studied:
- How to modify a pre-trained model to have inherent interpretability. 
- How to design tasks and evaluations catered to legal experts
- Tradeoffs between interpretability and abstraction
  
Many people assume that there is a tradeoff between inherent interpretability and model performance, and a model that's easier to understand loses some of the complexities. This work is both supporting and refuting that; while there is some amount of information lost in the "non-procedural" citations that have more abstract/analogous relationships between each other (e.g. don't have much keyword overlap, etc.), the **overall system performs better** after organizing the latent space more clearly.

## Post mortem
I like this paper, still. This was my first paper accepted to a top venue, after a year of being in review (it was first submitted to EMNLP in 2022, accepted to ACL 2023).

I think hindsight is 20-20 - many people complain that reviews are harsh now, but they were honestly just as harsh in 2022, if not harsher. I won't complain about them too much here, but let's just say peer review has never been kind to me. It also feels like another world, honestly. I don't know if the ideas we presented in this paper would be accepted now - it doesn't feel like inherent interpretability is as popular as mechanistic interpretability. It's gotten better recently, but I think that's an aspect of research that burns me out quickly - the feeling that my body of work is no longer interesting to anyone. I think nowadays, I'm more satisfied just pursuing what I find interesting.
