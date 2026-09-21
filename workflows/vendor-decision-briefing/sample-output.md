# Sample output: Vendor Decision Briefing

Text output of a production run on 2026-09-16, unedited (total model cost $0.58).

> This run also produced an image, which are not included here. Run the workflow in the demo to hear and see them.

---

🔎 Research Insights:

# Structured Research Notes

## Date checked

September 16, 2026.

## Company context used

Northstar Labs has 25 employees, four customer support agents, approximately 1,500 support conversations per month, email and in-app chat support channels, a requirement for a public knowledge base, reporting, and clear human escalation, and a budget target of $500 per month for four agents excluding taxes.

## Intercom

### Pricing basis

Intercom lists customer-service plans priced per seat per month, with Essential at $29 per seat/month, Advanced at $85 per seat/month, and Expert at $132 per seat/month at the listed rates.[1] For four agents, the listed plan subtotal would be $116/month on Essential, $340/month on Advanced, or $528/month on Expert before taxes, AI usage, and other add-ons.[1]

### Seat requirements

Intercom’s listed plans are seat-based, so each support agent who needs access would require a paid seat under the reviewed pricing model.[1] Any minimum-seat requirement beyond the per-seat pricing model was Not verified in the reviewed sources.[1][3]

### Email and chat support

Intercom’s reviewed pricing materials identify customer-service plans for managing customer conversations and support workflows, but plan-specific inclusion of both email and in-app chat for the required Northstar use case was Not verified in the reviewed sources.[1][2]

### Knowledge base support

Intercom materials reference Help Center functionality as part of its customer-service product set, but whether the required public knowledge base is included in each relevant plan was Not verified in the reviewed sources.[1][2]

### Reporting

Intercom’s pricing page references reporting capabilities across its customer-service plans, but the exact reporting depth included in each plan was Not verified in the reviewed sources.[1]

### Human escalation

Intercom’s Fin documentation describes Fin working with Intercom plans and handing conversations to the support team when human help is needed.[2] The exact escalation controls available by plan were Not verified in the reviewed sources.[1][2]

### Separately billed AI usage charges

Intercom lists Fin AI Agent usage separately from seat pricing and prices Fin at $0.99 per resolution in the reviewed materials.[1][2] Additional separately billed AI usage charges beyond Fin resolutions were Not verified in the reviewed sources.[1][2][3]

## Zendesk

### Pricing basis

Zendesk lists Suite plans priced per agent per month, including Suite Team at $55 per agent/month, Suite Growth at $89 per agent/month, and Suite Professional at $115 per agent/month at the listed rates.[4] For four agents, the listed plan subtotal would be $220/month on Suite Team, $356/month on Suite Growth, or $460/month on Suite Professional before taxes, AI usage, and other add-ons.[4]

### Seat requirements

Zendesk’s Suite pricing is agent-based, so each support agent who needs access would require an agent seat under the reviewed pricing model.[4] Any minimum-seat requirement beyond the per-agent pricing model was Not verified in the reviewed sources.[4][5]

### Email and chat support

Zendesk’s Suite materials list support for email and messaging across web, mobile, and social channels.[4][5] Whether Zendesk’s listed messaging capabilities fully satisfy Northstar’s specific in-app chat-widget requirement would require implementation validation and was Not verified in the reviewed sources.[4][5]

### Knowledge base support

Zendesk’s Suite materials list help center functionality in Suite plans.[4][5] Whether the required public knowledge base configuration is included without additional configuration or add-ons was Not verified in the reviewed sources.[4][5]

### Reporting

Zendesk’s Suite pricing materials list analytics and reporting capabilities, including prebuilt analytics dashboards in Suite plans.[4][5] The specific reporting depth required by Northstar was Not verified in the reviewed sources.[4][5]

### Human escalation

Zendesk’s reviewed Suite and pricing materials establish that the product supports agent-based customer service workflows.[4][5] A clear AI-to-human escalation path for the required Northstar workflow was Not verified in the reviewed sources.[4][5][6]

### Separately billed AI usage charges

Zendesk documentation describes AI-agent usage in terms of automated resolutions and resolution allowances.[6] The exact included allowance and any overage or additional-resolution price applicable to the relevant Suite plans were Not verified in the reviewed sources.[4][6]

## Help Scout

### Pricing basis

Help Scout uses contact-based pricing rather than per-seat pricing in the reviewed billing materials.[7][8] Help Scout’s contact-based billing documentation states that billing is based on contacts, so Northstar’s 1,500 monthly support conversations cannot be converted directly to a Help Scout bill without verifying the number of billable contacts.[8]

### Seat requirements

Help Scout’s reviewed pricing materials describe plans with unlimited users.[7] No per-agent seat requirement for the four Northstar support agents was verified in the reviewed sources.[7][8]

### Email and chat support

Help Scout’s reviewed pricing materials list shared inbox functionality and live chat/customer messaging through Beacon-related capabilities.[7] Whether the reviewed Help Scout capabilities fully satisfy Northstar’s specific in-app chat-widget requirement would require implementation validation and was Not verified in the reviewed sources.[7]

### Knowledge base support

Help Scout’s pricing materials list Docs knowledge base functionality.[7] Whether the required public knowledge base configuration is included without additional configuration or add-ons was Not verified in the reviewed sources.[7]

### Reporting

Help Scout’s reviewed pricing materials list reporting capabilities.[7] The specific reporting depth required by Northstar was Not verified in the reviewed sources.[7]

### Human escalation

Help Scout’s reviewed pricing materials show human-support channels such as inbox and chat functionality.[7] A clear AI-to-human escalation path for the required Northstar workflow was Not verified in the reviewed pricing, billing, and AI-pricing sources.[7][8][9]

### Separately billed AI usage charges

Help Scout’s AI Resolutions documentation identifies AI Resolutions as a separately billed AI usage item.[9] Additional separately billed AI usage charges beyond AI Resolutions were Not verified in the reviewed sources.[7][9]

## Sources

[1] https://www.intercom.com/pricing  
[2] https://www.intercom.com/help/en/articles/9061614-fin-and-intercom-plans-explained  
[3] https://www.intercom.com/help/en/articles/8344190-pricing-faqs  
[4] https://www.zendesk.com/pricing/  
[5] https://support.zendesk.com/hc/en-us/articles/4408846875034-About-the-Zendesk-Suite-plan-types  
[6] https://support.zendesk.com/hc/en-us/articles/10479587390106-Managing-resolution-allowances  
[7] https://www.helpscout.com/pricing/  
[8] https://docs.helpscout.com/article/1595-contact-based-fair-billing-policy  
[9] https://docs.helpscout.com/article/1746-ai-resolutions-pricing

---

📄 Generated Text:

[
  {
    "vendor": "Intercom",
    "candidate_plan": {
      "selection_status": "No fully feature-qualified candidate plan verified from the reviewed sources.",
      "priced_options": [
        {
          "plan": "Essential",
          "four_agent_monthly_estimate_usd": 116,
          "arithmetic": "4 support agents x $29 per seat/month = $116/month",
          "assumptions": "Each of the four support agents needs one paid seat; estimate excludes taxes, AI usage, and other add-ons."
        },
        {
          "plan": "Advanced",
          "four_agent_monthly_estimate_usd": 340,
          "arithmetic": "4 support agents x $85 per seat/month = $340/month",
          "assumptions": "Each of the four support agents needs one paid seat; estimate excludes taxes, AI usage, and other add-ons."
        },
        {
          "plan": "Expert",
          "four_agent_monthly_estimate_usd": 528,
          "arithmetic": "4 support agents x $132 per seat/month = $528/month",
          "assumptions": "Each of the four support agents needs one paid seat; estimate excludes taxes, AI usage, and other add-ons."
        }
      ]
    },
    "seat_pricing_basis": {
      "basis": "Per seat per month",
      "verified_prices_usd": {
        "Essential": 29,
        "Advanced": 85,
        "Expert": 132
      },
      "minimum_seats": "Not verified."
    },
    "ai_pricing_basis": {
      "separate_ai_charge_verified": true,
      "basis": "Fin AI Agent usage priced per resolution.",
      "price_per_resolution_usd": 0.99,
      "monthly_ai_estimate_usd": null,
      "unknowns": "Number of Fin resolutions for Northstar was not provided; additional separately billed AI usage charges beyond Fin resolutions were not verified."
    },
    "required_features": {
      "email_and_in_app_chat": "Not verified for Northstar's required plan-specific use case. Reviewed materials identify customer-service plans for customer conversations and support workflows, but plan-specific inclusion of both email and in-app chat was not verified.",
      "public_knowledge_base": "Not verified. Reviewed materials reference Help Center functionality, but whether the required public knowledge base is included in each relevant plan was not verified.",
      "reporting": "Partially verified. Pricing page references reporting capabilities across customer-service plans, but exact reporting depth by plan was not verified.",
      "clear_human_escalation": "Partially verified. Fin documentation describes Fin handing conversations to the support team when human help is needed; exact escalation controls by plan were not verified."
    },
    "budget_fit": {
      "budget_target_usd_per_month_excluding_taxes": 500,
      "seat_subtotal_fit_before_ai_taxes_addons": "Essential at $116 and Advanced at $340 are below the $500 target; Expert at $528 is above the $500 target.",
      "fit_including_ai": "Not verified because AI usage depends on Fin resolutions and any other AI charges were not verified."
    },
    "unknowns": [
      "Plan-specific inclusion of both email and in-app chat for Northstar's use case.",
      "Whether the required public knowledge base is included in each relevant plan.",
      "Exact reporting depth by plan.",
      "Exact human-escalation controls by plan.",
      "Any minimum-seat requirement beyond per-seat pricing.",
      "Monthly AI cost for Northstar because Fin resolution volume is unknown.",
      "Additional separately billed AI usage charges beyond Fin resolutions."
    ],
    "source_urls": [
      "https://www.intercom.com/pricing",
      "https://www.intercom.com/help/en/articles/9061614-fin-and-intercom-plans-explained",
      "https://www.intercom.com/help/en/articles/8344190-pricing-faqs"
    ]
  },
  {
    "vendor": "Zendesk",
    "candidate_plan": {
      "selection_status": "No fully feature-qualified candidate plan verified from the reviewed sources.",
      "priced_options": [
        {
          "plan": "Suite Team",
          "four_agent_monthly_estimate_usd": 220,
          "arithmetic": "4 support agents x $55 per agent/month = $220/month",
          "assumptions": "Each of the four support agents needs one paid agent seat; estimate excludes taxes, AI usage, and other add-ons."
        },
        {
          "plan": "Suite Growth",
          "four_agent_monthly_estimate_usd": 356,
          "arithmetic": "4 support agents x $89 per agent/month = $356/month",
          "assumptions": "Each of the four support agents needs one paid agent seat; estimate excludes taxes, AI usage, and other add-ons."
        },
        {
          "plan": "Suite Professional",
          "four_agent_monthly_estimate_usd": 460,
          "arithmetic": "4 support agents x $115 per agent/month = $460/month",
          "assumptions": "Each of the four support agents needs one paid agent seat; estimate excludes taxes, AI usage, and other add-ons."
        }
      ]
    },
    "seat_pricing_basis": {
      "basis": "Per agent per month",
      "verified_prices_usd": {
        "Suite Team": 55,
        "Suite Growth": 89,
        "Suite Professional": 115
      },
      "minimum_seats": "Not verified."
    },
    "ai_pricing_basis": {
      "separate_ai_charge_verified": "Not verified.",
      "basis": "Zendesk documentation describes AI-agent usage in terms of automated resolutions and resolution allowances.",
      "price_per_resolution_usd": null,
      "included_allowance": "Not verified for the relevant Suite plans.",
      "monthly_ai_estimate_usd": null,
      "unknowns": "Exact included allowance and any overage or additional-resolution price applicable to the relevant Suite plans were not verified."
    },
    "required_features": {
      "email_and_in_app_chat": "Partially verified. Suite materials list support for email and messaging across web, mobile, and social channels; whether this fully satisfies Northstar's specific in-app chat-widget requirement was not verified.",
      "public_knowledge_base": "Partially verified. Suite materials list help center functionality in Suite plans; whether the required public knowledge base configuration is included without additional configuration or add-ons was not verified.",
      "reporting": "Partially verified. Suite pricing materials list analytics and reporting capabilities, including prebuilt analytics dashboards; the specific reporting depth required by Northstar was not verified.",
      "clear_human_escalation": "Not verified. Reviewed materials establish agent-based customer-service workflows, but a clear AI-to-human escalation path for Northstar's workflow was not verified."
    },
    "budget_fit": {
      "budget_target_usd_per_month_excluding_taxes": 500,
      "seat_subtotal_fit_before_ai_taxes_addons": "Suite Team at $220, Suite Growth at $356, and Suite Professional at $460 are below the $500 target.",
      "fit_including_ai": "Not verified because AI-agent allowance, overage, and additional-resolution pricing for the relevant Suite plans were not verified."
    },
    "unknowns": [
      "Any minimum-seat requirement beyond per-agent pricing.",
      "Whether listed messaging capabilities fully satisfy Northstar's in-app chat-widget requirement.",
      "Whether the required public knowledge base configuration is included without additional configuration or add-ons.",
      "Specific reporting depth required by Northstar.",
      "Clear AI-to-human escalation path for Northstar's workflow.",
      "Exact included AI-agent resolution allowance and overage or additional-resolution price for relevant Suite plans."
    ],
    "source_urls": [
      "https://www.zendesk.com/pricing/",
      "https://support.zendesk.com/hc/en-us/articles/4408846875034-About-the-Zendesk-Suite-plan-types",
      "https://support.zendesk.com/hc/en-us/articles/10479587390106-Managing-resolution-allowances"
    ]
  },
  {
    "vendor": "Help Scout",
    "candidate_plan": {
      "selection_status": "No four-agent monthly estimate or fully feature-qualified candidate plan verified from the reviewed sources.",
      "priced_options": [
        {
          "plan": "Not verified.",
          "four_agent_monthly_estimate_usd": null,
          "arithmetic": null,
          "assumptions": "Reviewed billing materials state that Help Scout uses contact-based billing and plans with unlimited users; Northstar's 1,500 monthly support conversations cannot be converted directly to a bill without verifying the number of billable contacts."
        }
      ]
    },
    "seat_pricing_basis": {
      "basis": "Contact-based billing rather than per-seat pricing in the reviewed billing materials.",
      "verified_prices_usd": null,
      "minimum_seats": "No per-agent seat requirement for the four Northstar support agents was verified; reviewed pricing materials describe plans with unlimited users."
    },
    "ai_pricing_basis": {
      "separate_ai_charge_verified": true,
      "basis": "AI Resolutions identified as a separately billed AI usage item.",
      "price_per_resolution_usd": null,
      "monthly_ai_estimate_usd": null,
      "unknowns": "Additional separately billed AI usage charges beyond AI Resolutions were not verified."
    },
    "required_features": {
      "email_and_in_app_chat": "Partially verified. Reviewed pricing materials list shared inbox functionality and live chat/customer messaging through Beacon-related capabilities; whether these fully satisfy Northstar's specific in-app chat-widget requirement was not verified.",
      "public_knowledge_base": "Partially verified. Pricing materials list Docs knowledge base functionality; whether the required public knowledge base configuration is included without additional configuration or add-ons was not verified.",
      "reporting": "Partially verified. Reviewed pricing materials list reporting capabilities; the specific reporting depth required by Northstar was not verified.",
      "clear_human_escalation": "Not verified. Reviewed pricing materials show human-support channels such as inbox and chat functionality, but a clear AI-to-human escalation path for Northstar's workflow was not verified."
    },
    "budget_fit": {
      "budget_target_usd_per_month_excluding_taxes": 500,
      "seat_subtotal_fit_before_ai_taxes_addons": "Not verified because reviewed materials use contact-based billing and no supported four-agent monthly estimate was available.",
      "fit_including_ai": "Not verified because the monthly platform bill depends on billable contacts and AI Resolutions usage."
    },
    "unknowns": [
      "Number of billable contacts corresponding to Northstar's approximately 1,500 monthly support conversations.",
      "Four-agent monthly platform estimate.",
      "Whether Beacon-related capabilities fully satisfy Northstar's in-app chat-widget requirement.",
      "Whether the required public knowledge base configuration is included without additional configuration or add-ons.",
      "Specific reporting depth required by Northstar.",
      "Clear AI-to-human escalation path for Northstar's workflow.",
      "Additional separately billed AI usage charges beyond AI Resolutions."
    ],
    "source_urls": [
      "https://www.helpscout.com/pricing/",
      "https://docs.helpscout.com/article/1595-contact-based-fair-billing-policy",
      "https://docs.helpscout.com/article/1746-ai-resolutions-pricing"
    ]
  }
]

---

📄 Generated Text:

1. **Uncertain total monthly cost — Severity: High**
   - **Evidence:** Intercom’s four-seat subtotals range from $116 to $528 before AI, taxes, and add-ons; Fin costs $0.99 per resolution.[1][2] Zendesk’s four-agent subtotals range from $220 to $460, but applicable AI allowances and overage prices are **Not verified**.[4][6] Help Scout uses contact-based billing, so 1,500 conversations cannot be translated into a monthly price without the number of billable contacts; its AI Resolutions are billed separately.[7][8][9]
   - **Trial question:** Using Northstar’s actual contact and resolution volumes, what would the platform, add-on, and AI charges be for a representative month, and would the total remain below $500 excluding taxes?

2. **Minimum commitments and contract terms — Severity: Medium**
   - **Evidence:** Intercom is priced per seat and Zendesk per agent, but minimum seat counts beyond that basis are **Not verified**.[1][3][4][5] Help Scout advertises unlimited users under contact-based billing, but applicable minimum contact tiers or other commitments are **Not verified**.[7][8]
   - **Trial question:** What minimum seats, contact tier, billing period, usage commitment, and contract term would apply to the exact proposed configuration?

3. **Required capabilities may be gated by plan or add-on — Severity: High**
   - **Evidence:** No vendor has a fully feature-qualified plan in the reviewed comparison. Plan-specific inclusion of Intercom’s email, in-app chat, public knowledge base, and reporting requirements is **Not verified**.[1][2] Zendesk lists email, messaging, help-center, and analytics capabilities, but suitability and add-on requirements for Northstar’s configuration are **Not verified**.[4][5] Help Scout lists shared inbox, Beacon, Docs, and reporting, but the required configurations and reporting depth are **Not verified**.[7]
   - **Trial question:** On the quoted plan alone, can four agents operate email and an embedded in-app chat, publish a public knowledge base, and produce the required reports without upgrades or add-ons?

4. **Migration from the shared email inbox may require substantial effort — Severity: High**
   - **Evidence:** Northstar currently uses a shared email inbox. The reviewed evidence does not verify migration tooling, preservation of message history and attachments, contact deduplication, forwarding behavior, or the effort required for any vendor. Migration effort is therefore **Not verified**.
   - **Trial question:** Can a representative sample of the shared inbox be migrated with complete threads, attachments, timestamps, participants, and searchable history, and what manual work and downtime are required?

5. **Human escalation may be incomplete or poorly controlled — Severity: High**
   - **Evidence:** Intercom documents Fin handing conversations to a support team, but plan-specific escalation controls are **Not verified**.[1][2] A clear AI-to-human escalation path is **Not verified** for Zendesk or Help Scout in the reviewed sources.[4][5][6][7][8][9]
   - **Trial question:** Can a customer request a human at any point, and does escalation reliably preserve context, enter a visible agent queue, provide status expectations, and avoid trapping the customer in automation?

6. **Usage variability could make AI costs unpredictable — Severity: Medium**
   - **Evidence:** Intercom charges $0.99 per Fin resolution, but Northstar’s likely resolution volume is unknown.[1][2] Zendesk’s applicable included allowance and overage pricing are **Not verified**.[4][6] Help Scout separately bills AI Resolutions, but a supported monthly estimate and any additional AI charges are **Not verified**.[7][9]
   - **Trial question:** What percentage of Northstar’s 1,500 monthly conversations would generate a billable AI resolution, how is a resolution counted, and what controls or caps prevent unexpected charges?

---

📄 Generated Text:

**DECISION MEMO — Support Platform Trial**
To: Northstar Labs leadership | Date: September 16, 2026 | Status: no purchase approved

**Recommendation (judgment):** Trial **Zendesk Suite** first. Alternative: **Help Scout**.

**Basis in evidence.** Zendesk Suite four-agent subtotals are $220 (Team), $356 (Growth), and $460 (Professional) per month at listed rates, all below the $500 target before taxes, AI, and add-ons [zendesk.com/pricing]. Suite materials list email and messaging channels, help-center functionality, and prebuilt analytics dashboards [zendesk.com/pricing; support.zendesk.com Suite plan types]. Intercom's mid-tier Advanced is $340 for four seats, but Expert reaches $528, above target, and Fin is billed at $0.99 per resolution on top of seats [intercom.com/pricing; Fin plans article]. Help Scout bills by contacts with unlimited users, so no four-agent price can be derived from 1,500 monthly conversations without knowing billable contacts [helpscout.com/pricing; contact-based fair billing policy].

**Tradeoffs (judgment).** Zendesk offers the most verifiable price ceiling within budget and the broadest listed channel/KB/reporting coverage, at the cost of heavier configuration for a 25-person company. Help Scout's unlimited-user model could be cheapest for four agents but its cost is currently unquantifiable. Intercom's AI pricing is the most transparent ($0.99/resolution) but its seat costs are the most likely to breach $500.

**Unresolved (Not verified).** Plan-specific inclusion of an embedded in-app chat widget, public knowledge base, and required reporting depth for all three vendors; Zendesk's AI resolution allowance and overage price; Help Scout's billable-contact count and AI Resolutions price; minimum seats/contacts and contract terms; shared-inbox migration fidelity; AI-to-human escalation controls. A single-vendor recommendation is defensible only because Zendesk's price ceiling is verified; if Zendesk's AI overage pricing cannot be obtained in writing by Day 4, run Help Scout in parallel.

**Seven-day trial plan.** Days 1–2: sandbox, connect one email alias, embed widget in staging. Days 3–4: obtain written configuration quote; migrate 100 sample inbox threads. Days 5–6: route ~50 live conversations. Day 7: review.

**Acceptance criteria.** (1) Written quote ≤$500/month excluding taxes for four agents, with AI charges itemized. (2) On the quoted plan alone, one public KB article live, widget functional, and a report exporting first-response and resolution times. (3) 9 of 10 scripted escalations reach a human queue with full context within 60 seconds.

---

📄 Generated Text:

**Slide 1 — The Decision: Replace the Shared Inbox**

- Northstar's four support agents handle ~1,500 conversations per month in a shared email inbox with no knowledge base, reporting, or defined escalation path.
- Requirement: email plus in-app chat, a public knowledge base, reporting, and clear escalation to a human, at a target of $500/month for four agents excluding taxes, with AI usage charges itemized separately.
- Asked of leadership today: approval of a paid trial only. No purchase has been approved, and no vendor currently has a fully feature-qualified plan on the evidence reviewed.

---

**Slide 2 — Three-Vendor Comparison (Listed Rates, Four Agents)**

- **Zendesk Suite** (per agent/month): Team $220, Growth $356, Professional $460 — all below target before taxes, AI, and add-ons; AI resolution allowance and overage price **Not verified** [zendesk.com/pricing; support.zendesk.com].
- **Intercom** (per seat/month): Essential $116, Advanced $340, Expert $528 — Expert exceeds target; Fin AI billed separately and transparently at $0.99 per resolution [intercom.com/pricing; Fin plans article].
- **Help Scout**: contact-based billing with unlimited users, so no four-agent price can be derived from 1,500 conversations without the billable-contact count; AI Resolutions billed separately, price **Not verified** [helpscout.com/pricing; fair billing policy].

---

**Slide 3 — Recommendation: Seven-Day Zendesk Suite Trial**

- **Judgment:** trial Zendesk Suite first because it has the only verified price ceiling that stays under $500 for four agents, and Suite materials list email/messaging, help center, and prebuilt analytics in one package.
- **Fallback:** Help Scout runs in parallel if Zendesk's AI overage pricing is not obtained in writing by Day 4; its unlimited-user model may be cheapest but is currently unquantifiable.
- **Plan:** Days 1–2 sandbox, email alias, staging widget; Days 3–4 written configuration quote and 100 migrated sample threads; Days 5–6 route ~50 live conversations; Day 7 review.

---

**Slide 4 — Risks and Open Questions**

- **High — capability gating and total cost:** plan-specific inclusion of embedded in-app chat, public knowledge base, and required reporting depth is **Not verified** for all three vendors; AI charges could push any option past $500.
- **High — migration and escalation:** shared-inbox migration fidelity (threads, attachments, timestamps, search) is **Not verified** for every vendor, as is a controlled AI-to-human escalation path for Zendesk and Help Scout.
- **Medium — commitments and usage variability:** minimum seats or contact tiers, billing periods, and contract terms are **Not verified**; the share of 1,500 monthly conversations that would bill as AI resolutions is unknown.

---

**Slide 5 — Success Criteria and Approval Requested**

- **Price:** written quote of ≤$500/month excluding taxes for four agents, with AI usage charges itemized and any minimums or term commitments stated.
- **Function:** on the quoted plan alone — one public KB article live, in-app widget operational, and a report exporting first-response and resolution times; 9 of 10 scripted escalations reach a human queue with full context within 60 seconds.
- **Approval sought:** authorize the seven-day Zendesk Suite trial, with the Help Scout parallel trial as a conditional fallback. Purchase decision returns to leadership after Day 7.
