# Real Estate Lead Capture Automation

An n8n workflow that captures property inquiry leads, logs them to Google Sheets, and instantly alerts the team via Slack/email — so no inquiry sits unseen.

## What It Does

This workflow handles the first-touch process for property inquiries:

1. **Capture** — A lead's inquiry details are received.
2. **Store** — The lead is appended as a new row in Google Sheets, building a running, queryable log of every inquiry.
3. **Alert** — A notification is sent to the team (Slack/email) the moment a new lead comes in, so follow-up can happen immediately.

The result: every property inquiry is logged consistently and the team is alerted in real time, instead of inquiries sitting unread in an inbox.

## Why This Matters

In real estate, response speed is directly tied to conversion — a lead that waits hours for a reply is far more likely to go to a competing agent. This workflow closes that gap by logging and alerting on every inquiry the moment it happens.

## Workflow Breakdown

| Stage | Node Type | Function |
|---|---|---|
| Trigger | Manual Trigger | Initiates the workflow run |
| Storage | Google Sheets (Append Row) | Logs the lead's inquiry details into a running sheet |
| Notification | Slack/Email Node | Alerts the team of the new lead |

*(See Roadmap below — this is built and tested on a manual trigger; swapping to a live Webhook/Form trigger is the next step before production use.)*

## Tech Stack

- **n8n** — workflow orchestration
- **Google Sheets** — lead data storage
- **Slack/Email node** — team notification

## Setup

1. Import `real-estate-workflow.json` into your n8n instance: **Workflows → Import from File**.
2. Connect your Google Sheets credentials in the Storage node, pointing at your target spreadsheet.
3. Connect your Slack/email credentials in the Notification node.
4. Customize the notification message with your own team/channel details.
5. Run manually, or swap the trigger for a Webhook/Form trigger to fire automatically from a real inquiry form.

## Roadmap / Next Iteration

- Replace the manual trigger with a **Webhook or Form trigger** so it fires automatically when a real inquiry comes in.
- Add an **AI node** (Claude/OpenAI) to qualify or summarize leads before logging — e.g., flagging high-intent inquiries.
- Add lead source tagging (e.g., which listing or campaign generated the inquiry).

## Screenshot

![Workflow Canvas](workflow-diagram.png)

---

*Part of an ongoing portfolio of n8n automation workflows.*
