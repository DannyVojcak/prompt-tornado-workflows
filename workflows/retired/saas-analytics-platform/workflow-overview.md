# SaaS Analytics Platform Design Workflow

This workflow demonstrates how Prompt Tornado can orchestrate multiple AI capabilities from a single prompt to design a SaaS analytics utility for founders and operators.

In this example, the system produces a structured business design brief, a Python metrics calculation snippet, and a generated dashboard concept image.

The goal is to show how Prompt Tornado can break a complex prompt into multiple specialized tasks and route each task to the appropriate model.

---

## What This Workflow Demonstrates

- Structured product and business reasoning
- SaaS metrics and revenue model design
- Code generation for analytics calculations
- Image generation for dashboard visualization
- Multi-step, multi-output AI workflow orchestration

---

## Example Workflow Steps

### 1. Task Classification

Prompt Tornado analyzes the prompt and identifies multiple required outputs:

- structured text explanation
- Python code generation
- image generation

Each task is routed to the most appropriate model.

---

### 2. Text Generation

A language model generates the SaaS analytics design brief, including:

- core SaaS metrics
- revenue projection model
- early warning risk signals
- product feature blueprint

This step produces the primary structured explanation of the analytics system.

---

### 3. Code Generation

A code generation model produces a simple Python example showing how the system could calculate key SaaS metrics such as:

- Monthly Recurring Revenue (MRR)
- churn rate
- customer lifetime value (LTV)

This demonstrates how Prompt Tornado can generate executable logic alongside explanatory output.

---

### 4. Image Generation

An image generation model creates a concept visualization of the SaaS analytics dashboard, representing how founders or operators might monitor revenue metrics and business performance.

---

### 5. Unified Output

Prompt Tornado aggregates the outputs from each step and returns them in a single workflow run, organized into multiple output tabs:

- Text
- Code
- Image

This unified output allows users to move from prompt to a complete multi-format result without switching between multiple AI tools.

---

## Example Execution Pipeline

```
Prompt
↓
Task Classification
↓
Text Generation
↓
Code Generation
↓
Image Generation
↓
Unified Output
```

---

## Why This Workflow Matters

Modern AI systems rarely require a single response from a single model. Real-world workflows often involve multiple types of outputs, including explanations, code, visual assets, or structured artifacts.

Prompt Tornado acts as the orchestration layer that turns a single prompt into a coordinated, multi-step workflow executed across the best available models and providers.
