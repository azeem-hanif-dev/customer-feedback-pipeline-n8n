# Customer Feedback Pipeline (n8n)

An n8n workflow that turns a customer feedback form into a zero-touch pipeline: a submission comes in, gets logged straight to Google Sheets, and is set up to branch on sentiment so positive/negative responses can trigger different follow-up (a discount code, a support ping, etc.) instead of someone reading through a spreadsheet by hand.

![Workflow diagram](Google%20Customer%20Feedback.png)

## What it does

- **Form trigger** — collects Email, Name, Age, and a Comment sentiment (Positive / Neutral / Negative) via an n8n-hosted form.
- **Google Sheets sync** — appends every submission as a new row in a connected spreadsheet in real time, no manual copy-paste.
- **Conditional logic ready** — the pipeline is structured around a sentiment check (see diagram) so responses can be routed differently — e.g. auto-issuing a discount code for positive feedback, or flagging negative feedback for follow-up — rather than treating every submission the same way.

## Using it

1. Import `My workflow.json` into your n8n instance.
2. Open the **Append row in sheet** node and connect your Google Sheets credentials, then pick the target spreadsheet and sheet.
3. Activate the workflow — the form becomes live at its n8n-hosted URL and every submission lands in the sheet automatically.
4. Extend the `On form submission` → `Append row in sheet` connection with an `IF`/`Switch` node keyed on the Comment field to add the conditional branching (discount codes, alerts, etc.) shown in the diagram.

## Why this pattern

Manually sorting incoming feedback and deciding who gets a discount code doesn't scale past a handful of responses a week. This workflow removes the manual entry step entirely and gives you a single place (the sheet) to see every response land as it happens, with room to bolt on automated responses per sentiment.

---

### 🤝 About the Author

Built by **Sameer Faisal** — AI Developer | n8n Automation Specialist | Chatbot Builder

Open to freelance automation projects. If your team is still manually sorting feedback and sending discount codes — this is exactly what automation is for.

📩 [sameerf737@gmail.com](mailto:sameerf737@gmail.com) | [LinkedIn](https://www.linkedin.com/in/sameer-faisal-/) | [GitHub](https://github.com/Sameer051022)
