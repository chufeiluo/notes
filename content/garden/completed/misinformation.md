---
title: "mislc"
---

# Misinformation with legal consequences (MisLC): A new task towards harnessing societal harm of misinformation

[Github](https://github.com/chufeiluo/mislc)

## Project description
Misinformation, defined as false or inaccurate information, can result in significant societal harm when it is spread with malicious or even innocuous intent. The rapid online information exchange necessitates advanced detection mechanisms to mitigate misinformationinduced harm. Existing research, however, has predominantly focused on assessing veracity, overlooking the legal implications and social consequences of misinformation. 

In this work, we take a novel angle to consolidate the definition of misinformation detection using legal issues as a measurement of societal ramifications, aiming to bring interdisciplinary efforts to tackle misinformation and its consequence. 

- We introduce a new task: Misinformation with Legal Consequence (MisLC), which leverages definitions from a wide range of legal domains covering 4 broader legal topics and 11 fine-grained legal issues, including hate speech, election laws, and privacy regulations. 
- For this task, we advocate a two-step dataset curation approach that utilizes crowd-sourced checkworthiness and expert evaluations of misinformation. 
- We provide insights about the MisLC task through empirical evidence, from the problem definition to experiments and expert involvement. 

While the latest large language models and retrieval-augmented generation are effective baselines for the task, we find they are still far from replicating expert performance.
## Significance
This project studied:
- How to effectively cover more data in annotations while budgeting between general and specialized annotators
- How to practically apply the state-of-the-art in RAG to real-world data
- How to ground evaluations to be meaningful to another, specialized audience

## Post-mortem
Recently, I read other researchers discussing what is research that is done for the sake of getting published, and what is research that is meaningful. There are an obviously infinite number of projects we can pursue in one lifetime, but a finite amount of time, so it is important to choose the deeper explorations carefully. In this case, the misinformation project was just trying to transfer some of my ideas from [[legalhatespeech]] on a new task, but it did not synergize as well.

For one, the task of verifying misinformation is more complex - in some ways it is like deep research, where you recursively identify claims and then search the internet trying to verify them. Compared to hate speech, which can often be judged on a single social media post, misinformation is more multi-hop and leaves more room for ambiguity. The key is **context**. While the legal hate speech dataset isolated samples that were completely, unambiguously hateful, this dataset contained fragmented posts that were taken out of the original conversation.

For another, hate speech was just easier because there were more works published. It was easy to identify the gap that my research filled, and it was easier to justify why it was important without asking people to understand the value of my vision. While I did get to present my work at EMNLP, and some kind people found my work interesting, it feels like most people dismissed this work. I understand why - I've reviewed a fair share of papers that try to use social impact to cover for the fact that their experimental setup was weak. 

This paper also did not do any training, while hate speech used some self-training, etc. so the results weren't very comprehensive - it felt like it was trying to capitalize on RAG, which was trending at the time. It also felt kind of like clickbait - just another paper reviewing the shortcomings of current LLMs, LLMs are still far from solving problems, etc. etc.

I've come to realize that a lot of unoriginal thought comes from focusing too much on "common" knowledge, and defining your work as supporting or subverting what is widely accepted. This is okay when you are trying to present your work at a conference, but I've realized that this line of thinking during actual paper writing just makes extremely weak work. It obfuscates the ideas that were actually interesting (in my opinion), like the two-step pipeline of cheaper to more expensive annotation.

Also, I was just really burnt out at the time and I didn't do as much as I wanted for this paper. Like I previously mentioned, I didn't put model training into this paper - I actually did attempt tuning a 7b model with LoRA, but I started too late. I wanted to compare human to LLM-generated annotations. I wanted to do a more careful design of the RAG pipeline.

Of course, all of these feelings are normal for a project after it's done - this one is just memorable because it felt like a culmination of my burnout. Maybe I will do all of the above for my thesis, or for another paper. Maybe I will leave this project untouched for the rest of eternity. Either way, I think the regrets I have over this project have carried over into subsequent work.
