MailSentinel AI — Architecture

Overview

MailSentinel AI uses n8n to orchestrate email intake, AI-based classification, response drafting, approval-oriented processing, and database logging.

Technology Components

- n8n: Workflow orchestration and automation.
- Ollama: Local AI model runtime.
- Qwen3 14B: Email classification and response generation.
- PostgreSQL: Storage of workflow action logs.
- Webhook: Incoming email data intake.

Workflow Architecture

1. Incoming email data is received through an n8n webhook.
2. The workflow processes the email information.
3. Ollama receives the email content for AI classification.
4. The AI generates category, urgency, confidence, review status, and a response draft.
5. n8n evaluates the output and routes the message through the configured workflow.
6. Approval-related steps support human review.
7. PostgreSQL records relevant workflow actions.

Logical Data Flow

Incoming Email
      |
      v
  n8n Webhook
      |
      v
Email Processing
      |
      v
Ollama - Chat Model
      |
      v
AI Classification
      |
      v
Response Drafting
      |
      v
Review / Approval Flow
      |
      v
PostgreSQL Action Logging

Deployment

The project runs locally using Docker-based n8n and PostgreSQL services, with Ollama providing local AI inference.

Reliability and Security

- Validate incoming email data.
- Handle malformed AI responses.
- Monitor service availability.
- Protect webhook endpoints and credentials.
- Review AI-generated responses before sending.
- Avoid storing unnecessary personal email information.

Design Considerations

The architecture separates workflow orchestration, AI processing, and database logging to make the system easier to maintain and troubleshoot.

Note: The diagram represents the logical architecture. Refer to the actual n8n workflow for exact node connections and execution branches.
