MailSentinel AI — AI-Powered Email Automation

MailSentinel AI is an AI-powered email automation system built using n8n, Ollama, and PostgreSQL. It classifies incoming emails by category and urgency, generates response drafts, identifies messages requiring human review, supports approval workflows, and logs workflow actions in a database.

Features

- Automated email intake through webhooks
- AI-powered email classification
- Email urgency and confidence assessment
- AI-generated response drafts
- Human-review indicators
- Approval-oriented workflow
- PostgreSQL action logging
- Local AI inference using Ollama

Technology Stack

- n8n — Workflow automation
- Ollama — Local LLM runtime
- Qwen3 14B — Language model
- PostgreSQL — Database and action logging
- Webhooks — Email data intake and workflow triggering

How It Works

1. Receives incoming email data through a webhook.
2. Processes the email using the configured n8n workflow.
3. Uses the AI model to classify the message.
4. Generates a suggested response.
5. Identifies messages requiring human review.
6. Routes messages through the configured approval process.
7. Records workflow actions in PostgreSQL.

AI Output Fields

- category
- urgency
- confidence
- needs_human_review
- reason
- response_draft

Architecture

n8n orchestrates the automation workflow, Ollama performs local AI inference, and PostgreSQL stores action logs for traceability.

Safety and Limitations

AI classifications and generated drafts may contain errors. Human review is important before sending responses or taking consequential actions. Integration availability depends on the configured services and credentials.

Project Status

Completed AI automation project and portfolio prototype.

Author : 

Rohan Narlawar

GitHub: https://github.com/Rohan-nnnnnn

LinkedIn: https://www.linkedin.com/in/rohan-narlawar-149291354

Email: rohannarlawar31@gmail.com
