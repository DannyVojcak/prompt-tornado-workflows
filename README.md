# Prompt Tornado Workflow Examples

Example workflows for **[Prompt Tornado](https://www.prompt-tornado.com)**, a control plane for
multi-model AI workflows.

You describe what you want in one prompt. Prompt Tornado plans the steps, sends each step to the
model best suited to it, and returns one finished result: text, images, audio or code. Around every
run sits a control layer:

- **Spend caps:** a monthly limit that blocks or warns before you overspend.
- **Governance:** which models and regions your data may go to.
- **Approval for risky actions** before they run.
- **A full record** of what ran, which model ran it, and what it cost, exportable as evidence.

## Try it

- **Live demo, no sign-up:** https://app.prompt-tornado.com/demo runs the four workflows below.
- **The app:** https://app.prompt-tornado.com. The Free plan includes 10 runs a month.

▶ **Demo video**

[![Prompt Tornado Demo](https://img.youtube.com/vi/JU4CvqaB7us/maxresdefault.jpg)](https://youtu.be/JU4CvqaB7us)

---

## The four example workflows

These are the workflows in the app's Examples gallery, with the exact prompts and step plans it runs.
Each folder holds the prompt, an overview of the steps, and the unedited text output of a real
production run.

| Workflow | What it shows | Steps | Models in the sample run | Sample run cost |
|---|---|---|---|---|
| [Multilingual Product Launch](workflows/multilingual-launch/) | One announcement becomes four distinct Spanish deliverables: press copy, a video script, a social post and a voiceover script. Plus a narrated voiceover and a launch visual. | 4 | Claude Opus 5, Claude Sonnet 5, OpenAI TTS, FLUX (fal.ai) | $0.07 |
| [Vendor Decision Briefing](workflows/vendor-decision-briefing/) | Web research on three help-desk vendors, handed down a chain: a structured comparison, a risk review, a decision memo and a five-slide briefing. | 6 | Perplexity, GPT-5.5, GPT-5.6 Sol, Claude Opus 5, FLUX (fal.ai) | $0.58 |
| [Support Inbox Action Plan](workflows/support-inbox-action-plan/) | Eight support tickets triaged against an approved policy, including one that tries to override it, then structured ticket records, reply drafts and a manager's action brief. Nothing is sent: every reply is a draft. | 4 | Claude Opus 5, GPT-5.5, Claude Haiku 4.5 | $0.12 |
| [Billing Bug Fix & Independent Review](workflows/billing-bug-fix/) | Diagnose a revenue bug, patch it, write regression tests, then have a second vendor's model review the fix. The tests are written, not run. | 4 | GPT-5.6 Sol, Claude Opus 5 | $0.29 |

Models are chosen per step by the router, so a run today may use different ones. Each overview
lists the model that ran every step of its sample.

## Calling it from code

Runs can be started and fetched over the REST API with a personal API key created in the app. A
Python SDK exists but is not yet published to PyPI.

## Repository structure

```
prompt-tornado-workflows
├── README.md
├── assets/
└── workflows/
    ├── multilingual-launch/
    ├── vendor-decision-briefing/
    ├── support-inbox-action-plan/
    ├── billing-bug-fix/
    │   ├── prompt.txt
    │   ├── workflow-overview.md
    │   └── sample-output.md
    └── retired/                 earlier examples, no longer in the app
```

## Contributing

Workflow ideas and examples are welcome. Open a pull request with the prompt, a short overview of
the steps, and a sample output.

## License

This repository is provided for educational and demonstration purposes.
