# Autonomous AI Email Agent

An intent-driven email orchestration agent that classifies incoming mail in real time and routes it through the correct automated response, logging, or filtering pipeline — instead of relying on static keyword rules or manual triage.

## Overview

Most inboxes mix academic deadlines, career opportunities, networking outreach, business inquiries, and spam into a single unsorted stream. This agent sits between Gmail and the user, performing real-time intent classification on every incoming email and deciding what should happen next — draft a reply, log a lead, or silently filter noise — without manual sorting.

## How It Works

Every incoming email triggers a self-hosted n8n orchestration workflow. The agent uses Groq (inference) and Llama 3 (LLM) to classify intent, then routes the email down one of five pipelines:

1. **Academic Pipeline** — detects university deadlines and inquiries, drafts a professional response automatically.
2. **Career Tracker** — identifies job leads and interview requests, logs them into a Google Sheets CRM.
3. **Networking Hub** — recognizes peer/developer outreach, drafts a personalized reply to keep the connection warm.
4. **Business Intelligence** — qualifies client inquiries and drafts follow-up questions to pre-vet leads.
5. **Spam Guard** — flags high-risk or low-value mail and marks it as read, keeping it out of active notifications.

## Business Use Cases

This architecture generalizes beyond personal inbox management:

- **Automated Lead Qualification** — sales teams can auto-vet prospects and surface only high-value leads for follow-up.
- **Tier-1 Customer Support** — auto-draft responses to common queries, routing complex cases to a human agent.
- **Real-Time CRM Sync** — keep a sales pipeline updated without manual data entry.

## Tech Stack

| Layer | Technology |
|---|---|
| Orchestration | n8n (self-hosted, Docker) |
| Intelligence | Groq (inference) + Llama 3 (LLM) |
| Connectivity | Gmail API, Google Sheets API |

## Status

Core intent-classification and routing logic is live and functional. Demo materials use mock data to illustrate the different branches; the underlying decision logic runs against real inbox data. Voice/notification layers and expanded CRM fields are in progress.

## Notes

This project is part of an ongoing move toward fully agentic email workflows — replacing manual sorting with adaptive, LLM-driven routing.
