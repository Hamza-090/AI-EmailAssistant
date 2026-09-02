# NovaTech AI Email Assistant

An AI-powered customer support email automation workflow built with **n8n, Gmail, RAG, embeddings, vector search, and Gemini**.

The workflow reads incoming customer emails, understands the issue, retrieves relevant information from a knowledge base, generates a context-aware response, and keeps a **human approval step before sending the email**.

---

## Overview

The goal of this workflow is to reduce manual effort in handling repetitive customer support emails while keeping a human in control of the final response.

### Workflow

```text
Incoming Email
      ↓
Email Processing
      ↓
Classify / Analyze Email
      ↓
Retrieve Relevant Knowledge
      ↓
RAG Context
      ↓
Gemini Response Generation
      ↓
Human Review / Approval
      ↓
Send Email
```
Key Features
Automatically processes incoming support emails through Gmail.
Uses AI to analyze and classify customer queries.
Retrieves relevant information from a knowledge base using RAG (Retrieval-Augmented Generation).
Uses embeddings and vector search to find relevant knowledge.
Generates a context-aware response using Gemini.
Keeps a human approval step before sending the response.
Reduces the need for manually searching documentation for every customer query.
Keeps the workflow modular so individual stages can be modified independently.
Technologies Used
n8n – Workflow automation
Gmail API – Email retrieval and sending
Gemini – AI analysis and response generation
RAG – Retrieval-Augmented Generation
Embeddings – Knowledge representation
Vector Database / Vector Search – Relevant context retrieval
GitHub – Knowledge-base source
Webhooks / n8n nodes – Workflow orchestration
Workflow Components
1. Email Intake

The workflow receives customer emails and extracts the relevant information required for processing.

Typical information includes:

Sender
Email address
Subject
Message content
Thread information
2. Email Analysis

The incoming message is processed to determine the customer's request and provide structured information for the next stages of the workflow.

3. Knowledge Retrieval

The system searches the indexed knowledge base for information relevant to the customer's question.

This prevents the AI from relying only on its general knowledge and allows responses to be grounded in the available company documentation.

4. AI Response Generation

Gemini receives the customer's message together with the retrieved context and generates a suitable support response.

The response is designed to use the retrieved information instead of inventing unsupported answers.

5. Human Approval

Before anything is sent to the customer, the generated response goes through a human review step.

The reviewer can verify the response before the email is sent.

6. Email Delivery

After approval, the final response is sent through Gmail.

RAG Architecture
Knowledge Base
      ↓
Document Processing
      ↓
Embeddings
      ↓
Vector Store
      ↓
Similarity Search
      ↓
Relevant Context
      ↓
Gemini
      ↓
Grounded Email Response

This approach allows the assistant to answer questions using the project's knowledge base rather than relying entirely on the model's built-in knowledge.

Setup
Required Accounts / Credentials

The workflow requires credentials for the services used by the workflow, including:

Gmail
Gemini
GitHub / knowledge source
Vector database or vector-search service

Configure these credentials inside n8n before running the workflow.

Importing the Workflow
Open n8n.
Go to Workflows.
Import the provided .json workflow.
Configure the required credentials.
Verify the knowledge-base and vector-search configuration.
Test the workflow using a controlled email account.
Activate the workflow after validation.
Important Security Notes

Do not commit API keys, OAuth tokens, passwords, or other secrets to GitHub.

Before publishing this workflow:

Remove hard-coded API keys.
Remove access tokens.
Use n8n credentials instead of embedding secrets in nodes.
Replace any exposed credentials immediately.

The JSON file in this repository should be treated as a sanitized workflow export.

Project Goal

This project demonstrates how traditional email support can be combined with:

Generative AI
Retrieval-Augmented Generation
Vector search
Workflow automation
Human-in-the-loop systems
Gmail API integration

The result is an automated support pipeline that can process emails, retrieve relevant knowledge, generate responses, and keep a human involved before customer communication is sent.
