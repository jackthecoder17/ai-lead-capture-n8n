# AI Lead Capture & Qualification (n8n)

An n8n automation that takes inbound leads from a form, uses AI to qualify and score them, logs them to Google Sheets, and sends a personalized follow-up email — with an instant Slack alert for hot leads.

## What it does
1. A lead submits a form (name, email, company, service, budget, timeline, message)
2. Google Gemini classifies the lead as hot / warm / cold and scores it 1–10
3. Every lead is logged to Google Sheets
4. Hot leads trigger an instant Slack alert
5. Each tier gets a tailored auto-reply email
6. Failures retry automatically, and a separate error workflow alerts on Slack if something still breaks

## Stack
n8n · Google Gemini · Google Sheets · Gmail · Slack

## Setup
1. Import `lead-capture-v1.json` and `lead-capture-errors.json` into n8n
2. Add credentials: Google Gemini API key, Google Sheets OAuth, Gmail OAuth, Slack OAuth
3. Point the Google Sheets node at your own sheet (replace `YOUR_SHEET_ID_HERE`)
4. Set your own Slack channel (replace `YOUR_SLACK_CHANNEL_ID`)
5. Update the Calendly/booking link in the Hot email node
6. Activate both workflows, and set the Errors workflow as the Error Workflow in the main workflow's settings (Settings → Error Workflow)

## Result
Every lead gets a personalized reply in under a minute, and hot leads reach me before I've even opened my inbox.
