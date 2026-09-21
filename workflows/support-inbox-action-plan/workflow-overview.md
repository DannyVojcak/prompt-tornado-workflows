# Support Inbox Action Plan

Triage a synthetic support inbox against an approved policy, including one ticket that tries to override it, then produce structured ticket records, reply drafts, and a manager's action brief. Nothing is sent: every reply is a draft for human review.

This is one of the four workflows in the Prompt Tornado **Examples gallery**, and the public demo at
https://app.prompt-tornado.com/demo runs the same prompt with the same steps.

## Steps

| # | Step | What it does | Model that ran it |
|---|---|---|---|
| 1 | Writing | Triage all eight tickets. | `anthropic/claude-opus-5` |
| 2 | Writing | Convert the triage into a valid JSON array of exactly eight objects, one per ticket, in ticket order. | `openai/gpt-5.5` |
| 3 | Writing | Using the triage and the structured records, draft one customer response per ticket, labelled with its ticket ID and at most 65 words each. | `anthropic/claude-haiku-4-5` |
| 4 | Writing | Using the structured records and the response drafts, write a manager's action brief of at most 250 words. | `anthropic/claude-opus-5` |

The models are chosen per step by Prompt Tornado's router, so they can change as routing is
updated. The column shows the production run the sample output came from (2026-09-16, total model
cost $0.12).

## How the steps connect

- Step 1 starts from the prompt.
- Step 2 uses the output of step 1.
- Step 3 uses the outputs of steps 1 and 2.
- Step 4 uses the outputs of steps 2 and 3.

## Files

- `prompt.txt`: the exact prompt.
- `sample-output.md`: the text output of that run, unedited.
