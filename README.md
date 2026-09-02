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
