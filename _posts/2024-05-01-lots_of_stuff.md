---
title:  "Lots of stuff"
date:   2024-05-01
categories: Projects
teaser: /assets/images/red_room.jpg
header: /assets/images/red_room.jpg
og_image: /assets/images/red_room.jpg

tags: Computer_graphics, AI, NLP, C, C++, Assembly, Rust
---


It's been a couple of busy years since my last update in 2022, so I have quite a few updates, not only project/hobby related!

# 2023

During this year, I finally finished my Computer Science degree. This was a really busy one, as I had quite a few interesting but challenging courses, and I also took part in a research collaboration grant.

## Cool 2023 projects

### Computer Graphics project
We uploaded the raytracing & photonmapping engine we developed as part of the Computer Graphics course ([here](https://github.com/Sondeluz/Graphics_course_renderer)). It was purely developed in modern-ish C++ and has some niceties such as multithreading, use of acceleration structures, basic .obj file handling and an implementation of constructive solid geometry. As a showcase, we managed to render a recreation of Twin Peak's Red Room:

![A fancy Red Room](/assets/images/red_room.jpg)

Also, here's the obligatory Cornell Box:
![a lame, non-red room](/assets/images/lame_room.jpg)

### ARM Sudoku
Although this project was developed during 2021/2022, I only went around [uploading it](https://github.com/Sondeluz/ARM_sudoku) half a year ago. This is a fully functional Sudoku game playable through the `GPIO` and containing visualizations for both the `UART` console and the `GPIO` itself, for the `LPC2105 ARM7TDMI-S` CPU (simulated through `Keil uVision`). It was developed on a mix of C and ARM assembly (for interrupt handling, power saving...), with an event queue architecture.

### Research collaboration

Most of my time during 2022 and 2023 was dedicated to a research collaboration at the [SID group](http://sid.cps.unizar.es/). Thanks to this opportunity, I was able to delve into State-Of-The-Art techniques within fields such as Natural Language Processing (use of LLMs, NLP libraries...) and Semantic Information Retrieval (Knowledge Graphs, IR indexing engines such as elastic...). This collaboration has been extended until today, and we already have a conference paper pending for review. I can't wait to make the repo public, as it's my biggest project yet :)

# 2024

During this year, I finished my CS degree and moved to Barcelona for an MSc. in Intelligent Interactive Systems at Universitat Pompeu Fabra. During this year, I have been able to delve more into Natural Language Processing and AI/Machine Learning, with some Data Science in between. As a cherry on the cake, I'm also doing an intership at the European Commission's Joint Research Centre.

...It's been a way busier year.

## Cool 2024 projects

### IndexerMcIndexFace
During my research collaboration, I relied quite a lot on different [BM25 / BM25F](https://en.wikipedia.org/wiki/Okapi_BM25) implementations for document retrieval. I found most of them lacking in different aspects, such as parameter tweaking freedom or even transparency due to straight-up weird behaviors. I wanted to see just how hard it really was to implement a (very basic) BM25F ranking function, so I wrote [a really tiny-but-fast document indexing and retrieval system](https://github.com/Sondeluz/IndexerMcIndexFace
). I also used it as an excuse to play with [FSTs](https://en.wikipedia.org/wiki/Finite-state_machine) and Rust's parallelization capabilities, as I wrote it exclusively in Rust.


### Computational Semantics course
As part of my Master's, I took a course on Computational Semantics, where I worked on a wide range of NLP techniques, starting from "traditional" ones (use of WordNet and other corpora, static embeddings...) until reaching the State-Of-The-Art (contextual embeddings, multimodal LLMs...). I uploaded two of the most fancy projects [here](https://github.com/Sondeluz/ComputationalSemantics).

<img src="https://github.com/Sondeluz/ComputationalSemantics/blob/main/visualization_example.gif?raw=true" alt="Cool, rotating CLIP embeddings" />


### Conversational Agent
We also developed the inner systems of a Conversational Agent custom-tailored for Hotel and Restaurant requests, as part of a Natural Language Interaction course. I published its Named Entity Recognition module, which was the system I worked the most on, [here](https://github.com/Sondeluz/Conversational-Agent-NER). It consists of a NER system for the Semantic frame slot filling task of a Conversational Agent, trained and evaluated using the `MultiWOZ` dataset. This is made up of different components, as we went a bit beyond simply detecting direct mentions of entities in sentences:
- A NER system based on a Deberta-v3-base model, fine-tuned using the `flair` NLP library.
    - Detects directly mentioned slots (restaurant food types, restaurant and hotel names...)
    - Detects `question` and `dontcare` direct mentions
- A K-Nearest Neighbors classifier that is fed scaled sentence embeddings of user utterances using `bge-large-en-v1.5`, which was used to classify `question` and `dontcare` user utterances that indirectly refer to previously mentioned slots.

As a picture is worth a thousand words, here's how our NER system works when talking about SpongeBob entities (which we really hope the dataset didn't contain), and when the user prompts the system with a question alongside many other entity mentions.


![screenshot](/assets/images/conversational_agent_1.png)
![screenshot](/assets/images/conversational_agent_2.png)

The whole system will be uploaded soon, as might more projects that we did in other subjects!




