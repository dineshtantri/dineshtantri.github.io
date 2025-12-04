---
title: "Claude Code - Beyond Vibe Coding"
date: 2025-10-10
draft: false
---

Tools like Claude Code have opened up a new space between full blown coding/code completion and vibe coding. There are a number of roles like technical PMs who are probably not going to write code that goes into production but definitely need far more than what vibe coding platforms can give. 

Over the past month, I have been able to venture into new areas that would have not been easy without Claude Code:

1. Building out a personality engine that intercepts responses from a LLM and "injects" custom personality.
2. Testing out Redis performance with a 32000+ item dataset running off Docker and benchmarking performance against OpenSearch.
3. Building a PDF RAG system that uses GPT-4V for intelligent document processing and LangGraph for adaptive query workflows. The system processes PDFs by converting each page to images, using GPT-4V to extract structured text, then storing embeddings in Qdrant for semantic search.
4. Building a demo of Langfuse to decouple prompts from code.
5. And yes building a personal static website using Hugo and deploying it on Github pages! 
