# WhiteSky / Sky365 Integration Roadmap

> This document is the implementation handoff for the WhiteSky Technologies ecosystem. It separates what is already shipped from the next production-hardening steps.

## Shipped capabilities

| Capability | Repository | Current state | Primary entry point |
|---|---|---|---|
| WhiteSky bilingual ERP website | [`whitesky-technologies-erp`](https://github.com/saskw2010/whitesky-technologies-erp) | React + TypeScript + Vite, Arabic/English RTL support, solution pages, legal drafts, AI Tools Hub, contact flow and ROI calculator | [whitesky.tech](https://whitesky.tech) |
| RAG AI Agent API | [`WhiteSky.AI.Api`](https://github.com/saskw2010/WhiteSky.AI.Api) | .NET 8 Web API using Microsoft Semantic Kernel; chat endpoint and retrieval-ready service boundary | [API repository](https://github.com/saskw2010/WhiteSky.AI.Api) |
| Developer Portal | [`Sky365-Engineering-Knowledge-Base/Developer-Portal`](https://github.com/saskw2010/Sky365-Engineering-Knowledge-Base/tree/main/Developer-Portal) | Authentication, ERP, POS and AI endpoint documentation with OpenAPI baseline | [Portal folder](https://github.com/saskw2010/Sky365-Engineering-Knowledge-Base/tree/main/Developer-Portal) |
| Career Navigator | [`career-navigator`](https://github.com/saskw2010/career-navigator) | Vue 3 dashboard, Arabic career coach, local skill matching, match scores and readiness insights | [Career repository](https://github.com/saskw2010/career-navigator) |
| Reference product | [WytSKY](https://wytsky.com) | Product and ecosystem reference for Sky365 positioning | [wytsky.com](https://wytsky.com) |

## Recommended production sequence

### P0 — Trust and data boundaries

1. Replace all sample API values, contact details and performance claims with verified company data before public launch.
2. Move secrets, database connection strings and vector-store credentials to server-side environment variables. Never place them in the React or Vue bundles.
3. Add tenant isolation to every ERP and RAG query. The retrieval layer must filter by `tenant_id`, user role and document permissions before context reaches the model.
4. Add structured logging, correlation IDs, request rate limits and audit events for chat, document ingestion and ERP mutations.

### P1 — Dynamic RAG with SQL Server

The preferred path is a hybrid retrieval pipeline rather than allowing an LLM to run arbitrary SQL:

1. **Ingestion:** capture approved ERP metadata, policy documents and operational summaries into a canonical document model.
2. **Indexing:** create embeddings for approved text chunks and store metadata such as tenant, module, document type, language, effective date and access scope.
3. **Structured facts:** expose read-only parameterized views or stored procedures for metrics such as revenue, inventory, receivables and payroll summaries.
4. **Query planning:** classify each user question as semantic, structured or hybrid. Use vector retrieval for policy and narrative questions; use allow-listed views for numeric questions; combine both for explanations grounded in live facts.
5. **Answer contract:** return answer, citations, data timestamp, confidence and a safe refusal when the request exceeds user permissions or available evidence.
6. **Evaluation:** maintain a golden set of Arabic and English questions and measure groundedness, retrieval recall, citation correctness, latency and refusal quality before every release.

### P1 — Developer experience

1. Publish the OpenAPI file from the running API build, not from a manually edited copy.
2. Add examples for Arabic requests, pagination, idempotency, error envelopes and webhook verification.
3. Generate typed clients for .NET and TypeScript and version them with the API contract.
4. Add a sandbox environment with synthetic data and an API-key lifecycle that is separate from production.

### P2 — Career intelligence

1. Keep the local matcher as a deterministic fallback and record the reasons behind every score.
2. Add an optional model-assisted ranking layer only after consent, explainability and bias tests are defined.
3. Separate candidate data from analytics, encrypt sensitive fields and define retention/deletion workflows.
4. Add employer-side vacancy ingestion and a skills taxonomy mapped to Arabic and English synonyms.

### P2 — Ecosystem extensions

The following initiatives are valuable but should follow the P0/P1 controls above: workflow automation through n8n, a governed Knowledge OS, visual reporting through Colibri or another BI layer, a Blazor/.NET administrative console, and a public integration marketplace. Each should consume versioned APIs rather than connect directly to production tables.

## Definition of done for Dynamic RAG

A release is ready for pilot when it has tenant-filtered retrieval, parameterized SQL views, Arabic/English evaluation cases, citations in every factual answer, traceable audit logs, a documented refusal policy, and an operator runbook for data freshness and failed ingestion.
