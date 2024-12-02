# NovelWriter
## Description

This repository contains Python code to generate a novel using the OpenAI API. It was created as part of NaNoGenMo 2024 ([**completed**](https://github.com/NaNoGenMo/2024/issues/31)). The first version is not fully automated, but it used to generate a 52,000-word novel: [Echoes of Terra Nova](combined_novel.md)

The goal was to explore the potential of LLMs for long-form storytelling, breaking the problem into manageable pieces rather than attempting a single-pass generation.

## Overview
The novel generation process involved hacking together some Python code to use various LLMs, including GPT-4, o1-mini and o1-preview, in a structured workflow that incrementally builds the story. 

The output isn't at the level of human-written prose but serves as a proof of concept for what's possible using iterative prompts and careful planning.


## Project Goals

1. Demonstrate the feasibility of using LLMs to write a novel by breaking down the creative process into smaller, manageable tasks.
2. Participate in NaNoGenMo by generating 50,000 words of coherent text using AI. ([**completed**](https://github.com/NaNoGenMo/2024/issues/31))
3. Develop an approach that allows for improvement over time, ideally leveraging GPT-4's strengths through iterative prompts.

I've seen A lot of people argue that it's not possible to write a novel with current LLMs, mainly due to the context window limitations or perhaps due to intelligence-level. However, neither of those are really the issue.

The idea is that since LLMs can't generate huge amounts of text at once, they're unsuitable for creating a cohesive story. But honestly, the idea of one-shotting a novel in a single LLM pass seems impractical—even for human authors, writing a novel is an iterative process. Authors like Stephen King might write fast, but they certainly don't write without planning, contemplation, and rewriting. So why would we expect an AI to one-shot a novel?

Smarter LLMs at the level of a professional writer with a giant context window may not still "solve" the problem, but I think some ability to plan and iteratve upon an answer should work. So a more advanced version of o1, or an agent-based approach.

That being said, I've had a hypotheis for a while that GPT4 is sufficiently advanced that it could produce a novel if using multiple prompts and adding some extra process to ensur coherency. I think this project showing a path towards that goal.

## The Generation Process

The novel generation process is broken down as follows:

1. Generate Background: Start by generating background details for the story universe—this includes characters, factions, and general world-building elements. (I used GPT-4o for this step.)

2. Define Relationships: Create a web of relationships between the factions and characters. This adds depth to interactions and motivations. (Again, using GPT-4o.)

3. High-Level Outline: Develop a high-level story outline. I initially tried GPT-4o, but found it to struggle with the size of the prompt, so I ended up using o1-mini for generating structured outlines. This part could use further improvement, I think multiple prompts with GPT-4o would work.

4. Chapter Outlines: Generate outlines for each chapter. This is the weakest part of the process at the moment—probably because I didn't iterate enough. (Used GPT-4o, though o1-mini might have worked better here. I hope to rework this to use multiple GPT-4o prompts)

5. Write Chapters: Expand on the chapter outlines to create the full text of each chapter. I ended up using o1-preview to produce enough text quickly for NaNoGenMo. That was a bit expensive, but it worked. The first drafts weren't quite 50k when combined though.

6. Rewrite and Expand: Finally, to meet the 50,000-word requirement, I asked GPT-4o to review each chapter and add any missing details. This part was a bit rushed, but it helped fill in the gaps and meet the word count.

Overall, I believe this process could be streamlined and improved, especially using GPT-4o over multiple iterations. I want to go back and refine my code to rely solely on GPT-4o, as I think it has enough power to handle this step-by-step approach more effectively.

The project is still far from perfect, but it's exciting to see how far we can push LLMs in creative writing. I think with more iteration, we can get closer to producing something that feels more cohesive and compelling—even if we're not quite at the point of a "one-shot novel."

