NovelRAG: Character Backstory Consistency Checker
The Problem
Large Language Models (LLMs) often struggle to digest and retain complex details from long-form content, such as entire novels. When authors, editors, or game developers want to write a new backstory or fanfiction for an established character, standard LLMs hallucinate or lose track of the vast lore, leading to plot holes and inconsistencies.

The Solution
This repository implements a robust Retrieval-Augmented Generation (RAG) pipeline enhanced with advanced NLP techniques to solve the long-context problem. Given an entire novel, a specific character, and a proposed backstory, the pipeline breaks down the massive text, retrieves highly relevant character facts, and predicts whether the new backstory is strictly consistent with the established lore.

Key Features
Bypasses LLM Context Limits: Efficiently processes massive texts (like entire novels) without overflowing the LLM's context window by utilizing targeted RAG techniques.

Atomic Fact Extraction: Breaks down complex character histories into verifiable "atomic statements" (isolated, single-fact sentences) for highly accurate comparisons.

Automated Consistency Verdicts: Cross-references the proposed backstory (hypothesis) against the retrieved atomic facts to output a definitive verdict (support, contradict, or neutral).

Detailed Scoring: Generates a final consistency score based on the ratio of supporting vs. contradicting facts found in the novel.

Powered by LangChain & LangSmith: Fully observable pipeline with built-in tracing and debugging for complex LLM calls.

How it Works
Ingestion & Chunking: The novel is ingested, chunked, and embedded into a vector database.

Retrieval: When given a character and a backstory (hypothesis), the pipeline retrieves the most relevant chunks of lore from the vector store.

Fact Decomposition: The retrieved chunks are broken down into individual atomic facts.

Consistency Checking: An LLM evaluates the hypothesis against these atomic facts, mapping out contradictions and supporting statements to output a final verdict.
