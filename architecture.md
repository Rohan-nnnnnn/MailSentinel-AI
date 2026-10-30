MailSentinel AI — System Architecture

Overview

MailSentinel AI is an AI-powered email classification and response automation system built using n8n, Ollama, PostgreSQL and Notion.

The system processes incoming emails, classifies their intent and urgency, retrieves relevant business policy information from Notion, generates context-aware response drafts and routes sensitive or uncertain cases for human approval.

Architecture Components

1. Email Intake

The workflow receives incoming email data through a configured webhook.

The incoming email is processed to extract relevant information such as sender, subject and message content.

2. Email Classification

Ollama processes the email using an LLM-based classification stage.

The classifier generates structured information including:

- Email category.
- Urgency level.
- Confidence score.
- Human review requirement.
- Classification reasoning.
- Response draft information.

3. Knowledge Retrieval — Notion RAG

Notion serves as the knowledge source for business policies and reference information.

The workflow retrieves relevant policy content based on the incoming email context.

The retrieved information is provided to the AI response-generation stage to support context-aware responses.

This allows the system to use existing business knowledge rather than relying entirely on the model's general knowledge.

4. Response Generation

The AI uses the email content, classification results and relevant retrieved policy information to prepare a response draft.

The generated response is intended to follow the available business policy context.

5. Human Approval

Emails requiring human review are routed through an approval process.

The reviewer can approve or reject the proposed response.

The workflow also handles responses that do not require manual review, according to the configured classification and routing logic.

6. PostgreSQL Logging

PostgreSQL stores relevant classification and workflow execution information.

The database maintains records of classifier results and subsequent workflow actions.

This supports execution tracking and auditing.

7. Final Processing

Based on the classification and approval outcome, the workflow follows the configured processing path.

The system records the corresponding action and maintains the relevant execution history.

Processing Flow

Email Intake → Content Extraction → AI Classification → Notion Knowledge Retrieval → Context-Aware Response Generation → Human Approval or Automated Processing → PostgreSQL Logging

Architecture Principles

Modular Workflow Design

Each processing stage performs a specific responsibility, allowing individual components to be maintained and modified independently.

Knowledge-Grounded Responses

Notion provides business-specific reference information to support more relevant and context-aware response generation.

Human-in-the-Loop Control

Sensitive or uncertain email cases can be escalated for human review instead of relying entirely on automated decisions.

Structured AI Output

The classification stage produces structured fields that support downstream routing and processing.

Execution Tracking

PostgreSQL maintains workflow records to support monitoring and auditing.

Limitations

- Classification quality depends on the selected LLM and email content.
- Knowledge retrieval depends on the availability and quality of Notion reference information.
- Generated responses require appropriate human oversight.
- The system does not guarantee perfect classification or policy interpretation.

Technology Stack

- n8n — Workflow orchestration and automation.
- Ollama — Local LLM inference.
- PostgreSQL — Classification and execution logging.
- Notion — Business knowledge source for RAG.
- Webhooks — Email intake and workflow triggering.

