MailSentinel AI — Setup Guide

Prerequisites

- Docker Desktop
- n8n
- Ollama
- PostgreSQL
- Qwen3 14B model
- Required integration credentials

1. Start the Services

Start the existing Docker containers for n8n and PostgreSQL.

Verify that the services are running.

Default local endpoints:

- n8n: http://localhost:5678
- Ollama: http://localhost:11434
- PostgreSQL: localhost:5432

2. Prepare Ollama

Ensure Ollama is installed and the required model is available.

Run:

```bash
ollama pull qwen3:14b
```

Verify the installed model:

```bash
ollama list
```

3. Configure PostgreSQL

- Ensure PostgreSQL is running.
- Verify database connection settings.
- Configure the PostgreSQL credentials in n8n.
- Confirm that the required action-log table exists.

4. Configure Integrations

Open n8n and configure the required credentials using its credential manager.

Verify that the webhook, AI model endpoint, and database connections are correctly configured.

5. Import the Workflow

- Open the n8n interface.
- Import the actual MailSentinel AI workflow export.
- Review the nodes and connections.
- Reconfigure credentials if required.
- Verify the webhook and Ollama endpoints.
- Save the workflow.

6. Test the Workflow

Submit a sample email through the webhook.

Verify:

- Email intake works.
- AI classification produces the expected fields.
- Response drafting works.
- Human-review routing behaves correctly.
- Approval steps execute as configured.
- PostgreSQL records the required actions.

7. Security Recommendations

- Never publish API keys or passwords.
- Protect webhook endpoints.
- Avoid storing unnecessary personal email information.
- Review AI-generated drafts before sending them.
- Use synthetic email data for demonstrations.

Troubleshooting

Ollama Connection Failure

Verify that Ollama is running and that n8n can reach its configured endpoint.

PostgreSQL Connection Failure

Check the hostname, port, database name, username, and password.

AI Output Issues

Inspect the model response and verify that the expected JSON fields are returned.

Workflow Execution Failure

Check the n8n execution history and inspect the first failing node.

Completion

After setup, run the workflow with sample emails and verify the expected processing, review, and logging behavior.
