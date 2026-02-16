---
title: "test-time-epiplexity"
---

# Asking better questions by estimating Test-time epiplexity
I think a lot about new ways AI can collaborate with humans, not just statically/passively churn on a task. Cursor and Claude Code can ask a user questions, which is a start, but how good is a language model's guage of what needs to be asked? e.g. I notice Claude Code really only asks high-level, conceptual questions but still gets minor implementation details wrong because it made some incorrect assumptions.

The main goal of this project is getting a language model to ask better questions, which would reduce the overall amount of tokens required to complete a specific task.

## Messier notes

Most questions are asked to clarify and align model beliefs with human beliefs when there are ambiguities in the known context (epistemic) or the model’s proposed answer (aleatoric)

[To Believe or Not to Believe Your LLM](https://arxiv.org/abs/2406.02543)

We want the questions to be important and minimal - don’t ask too many stupid questions

We want to ask critical questions - a balance between the cost of an external party answering the question, and the model answering the question

We want the model to continually refine its own internal state until it hits a point where it cannot further disambiguate, in which case it asks the user

i.e. we want the question that maximizes the student’s model of the problem given, i.e. minimizes the randomness of the outcome

[From Entropy to Epiplexity: Rethinking Information for Computationally Bounded Intelligence](https://arxiv.org/abs/2601.03220)

Epiplexity assumes that there is access to the training process - either a student that can learn from a teacher model, or a model trained from random initialization (?)

> While in this work we focus primarily on computational constraints which we consider most fundamental, other constraints such as memory or within a given function
class F can be accommodated by replacing PT with PF, and may be important for understanding particular phenomena.3
3. One such possibility is to constrain the function class to all models reachable by a given optimization procedure with a given neural network architecture.
>
