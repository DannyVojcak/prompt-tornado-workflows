# Billing Bug Fix & Independent Review

Diagnose a revenue bug in synthetic billing code, patch it, and write regression tests, then have an independent reviewer check the fix against the spec and the expected totals. Nothing is executed: the tests are written, not run.

This is one of the four workflows in the Prompt Tornado **Examples gallery**, and the public demo at
https://app.prompt-tornado.com/demo runs the same prompt with the same steps.

## Steps

| # | Step | What it does | Model that ran it |
|---|---|---|---|
| 1 | Writing | Diagnose the bug. | `openai/gpt-5.6-sol` |
| 2 | Code | Using the diagnosis, write the corrected billing_mrr.py: the Subscription dataclass and monthly_recurring_revenue with the same signature. | `openai/gpt-5.6-sol` |
| 3 | Code | Using the diagnosis and the patched module, write pytest tests in a file named test_billing_mrr.py that imports from billing_mrr. | `openai/gpt-5.6-sol` |
| 4 | Writing | Independently review the patch and the tests against the MRR definition and the diagnosis. | `anthropic/claude-opus-5` |

The models are chosen per step by Prompt Tornado's router, so they can change as routing is
updated. The column shows the production run the sample output came from (2026-09-16, total model
cost $0.29).

## How the steps connect

- Step 1 starts from the prompt.
- Step 2 uses the output of step 1.
- Step 3 uses the outputs of steps 1 and 2.
- Step 4 uses the outputs of steps 1, 2 and 3.

## Files

- `prompt.txt`: the exact prompt.
- `sample-output.md`: the text output of that run, unedited.
