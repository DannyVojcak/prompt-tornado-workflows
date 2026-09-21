# RAG Research Workflow

This workflow demonstrates how Prompt Tornado can execute a structured, multi-step research workflow from a single prompt.

In this example, the system is asked to produce an executive-ready architecture brief on modern enterprise Retrieval-Augmented Generation (RAG) systems, using high-quality technical sources and strict formatting requirements. The workflow also includes a visual generation component to create a concept image related to the topic.

## What this workflow demonstrates

- source-quality-aware research prompting
- structured output requirements
- technical synthesis across multiple subtopics
- evidence-based summarization
- multimodal workflow execution across research and image generation tasks

## Example Steps

1. **Task Classification**
   - Detect that the prompt contains both research and image-generation tasks.

2. **Research Step**
   - Gather and prioritize highly credible technical sources related to enterprise RAG architecture.

3. **Synthesis Step**
   - Consolidate findings into a structured architecture brief using the exact required headings and formatting.

4. **Image Generation Step**
   - Generate a concept image representing the architecture and retrieval theme described in the prompt.

5. **Unified Output**
   - Return the research brief and image output as part of a single workflow result.

## Example Pipeline

Prompt  
↓  
Task Classification  
↓  
Research Agent  
↓  
Synthesis Agent  
↓  
Image Generation Agent  
↓  
Unified Output
