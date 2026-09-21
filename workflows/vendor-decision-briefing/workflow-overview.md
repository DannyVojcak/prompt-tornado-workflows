# Vendor Decision Briefing

Research three help-desk vendors against a stated budget, then hand the evidence down a chain that produces a structured comparison, a risk review, a decision memo, and a five-slide executive briefing.

This is one of the four workflows in the Prompt Tornado **Examples gallery**, and the public demo at
https://app.prompt-tornado.com/demo runs the same prompt with the same steps.

## Steps

| # | Step | What it does | Model that ran it |
|---|---|---|---|
| 1 | Web research | Research the three vendors using their official product, pricing, and help documentation. | `perplexity/preset/medium → openai/gpt-5.5` |
| 2 | Writing | Using ONLY the research from the previous step, output a valid JSON array with one object per vendor. | `openai/gpt-5.5` |
| 3 | Writing | Review the research and the structured comparison against the stated requirements and budget for Northstar Labs. | `openai/gpt-5.6-sol` |
| 4 | Writing | Write a decision memo of at most 350 words recommending one vendor to trial first and naming one alternative. | `anthropic/claude-opus-5` |
| 5 | Writing | Turn the decision memo into a five-slide executive outline: (1) the decision and the business need; (2) the three-vendor comparison; (3) the recommended trial and its rationale; (4) risks and unanswered questions; (5)… | `anthropic/claude-opus-5` |
| 6 | Image | A refined editorial illustration of a small customer support team coordinating three incoming communication channels at a calm, organized service desk. | `fal_ai/fal-ai/flux/schnell` |

The models are chosen per step by Prompt Tornado's router, so they can change as routing is
updated. The column shows the production run the sample output came from (2026-09-16, total model
cost $0.58).

## How the steps connect

- Step 1 starts from the prompt.
- Step 2 uses the output of step 1.
- Step 3 uses the outputs of steps 1 and 2.
- Step 4 uses the outputs of steps 1, 2 and 3.
- Step 5 uses the outputs of steps 2, 3 and 4.
- Step 6 starts from the prompt.

## Files

- `prompt.txt`: the exact prompt.
- `sample-output.md`: the text output of that run, unedited.
