# Multilingual Product Launch

Localize a product announcement into Spanish, create launch marketing versions, and generate a professional voiceover.

This is one of the four workflows in the Prompt Tornado **Examples gallery**, and the public demo at
https://app.prompt-tornado.com/demo runs the same prompt with the same steps.

## Steps

| # | Step | What it does | Model that ran it |
|---|---|---|---|
| 1 | Writing | Using the English product announcement in the user prompt, produce section A of the output: A) Spanish Launch Announcement — Write a complete, polished Spanish localization of the announcement. | `anthropic/claude-opus-5` |
| 2 | Writing | Using the Spanish launch announcement from the previous step, produce sections B, C and D: B) Launch Video Script (Spanish) — 2–3 short sentences of spoken narration for a product launch video. | `anthropic/claude-sonnet-5` |
| 3 | Voiceover | Generate a spoken Spanish voiceover of the launch video script. | `openai/gpt-4o-mini-tts` |
| 4 | Image | A cinematic global product launch event on a dramatic stage, illuminated by deep blue and gold lighting, with volumetric light beams cutting through a dark auditorium. | `fal_ai/fal-ai/flux/schnell` |

The models are chosen per step by Prompt Tornado's router, so they can change as routing is
updated. The column shows the production run the sample output came from (2026-09-21, total model
cost $0.07).

## How the steps connect

- Step 1 starts from the prompt.
- Step 2 uses the output of step 1.
- Step 3 uses the output of step 2.
- Step 4 starts from the prompt.

## Files

- `prompt.txt`: the exact prompt.
- `sample-output.md`: the text output of that run, unedited.
