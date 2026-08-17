# 🌐 WytSKY & Sky 365 Developer Portal

Welcome to the official Developer Portal for **WytSKY Solutions** and the **Sky 365 Enterprise Suite**. This portal provides engineering teams, enterprise clients, and third-party integrators with comprehensive documentation, API specifications, authentication guides, and SDKs to seamlessly integrate with our ecosystem.

---

## 🚀 Quick Access Links & Navigation

| Section | Description | Direct Access Link |
| :--- | :--- | :--- |
| **Authentication & Security** | OAuth 2.0 / JWT token generation and scopes | [View Auth Specs](#1-authentication--security) |
| **Sky ERP REST APIs** | Core financial, warehouse, and HR endpoints | [Explore ERP APIs](#2-sky-erp-rest-apis) |
| **Sky POS (wePOS) Integration** | Live cart sync, cashier terminals, and barcode webhooks | [Explore POS APIs](#3-wepos-integration-guide) |
| **Sky AI Agent / RAG API** | Semantic Kernel endpoints and vector search queries | [Explore AI Endpoints](#4-sky-ai--rag-api) |
| **SDKs & Code Samples** | C# / .NET 8 and TypeScript client libraries | [Download SDKs](https://github.com/saskw2010/Sky365-Engineering-Knowledge-Base/tree/main/Developer-Portal/sdks) |

---

## 1. Authentication & Security
All requests to the Sky 365 API must include a valid Bearer token in the `Authorization` header:

```http
Authorization: Bearer sk_live_wytsky_xxxxxxxxxxxxxxxx
```

### Endpoints:
- `POST /api/v1/auth/token`: Exchange client credentials for a JWT access token.
- `POST /api/v1/auth/revoke`: Revoke an active session token.

---

## 2. Sky ERP REST APIs
The Sky ERP API allows enterprise systems to synchronize master data, manage multi-warehouse inventory, and process payroll securely.

### Core Endpoints:
- **Inventory Management:**
  - `GET /api/v1/erp/warehouses`: List all connected warehouses and stock levels.
  - `POST /api/v1/erp/stock/adjust`: Perform stock adjustments with audit logging.
- **Financial Ledger:**
  - `GET /api/v1/erp/financials/balance-sheet`: Retrieve real-time fiscal summaries.

---

## 3. wePOS Integration Guide
Designed for seamless retail operations, the wePOS API bridges physical cash registers with cloud ERP databases.

- `POST /api/v1/pos/transactions`: Submit offline or online point-of-sale transactions.
- `GET /api/v1/pos/terminals/status`: Check live connectivity of outlet terminals.

---

## 4. Sky AI & RAG API
Empower your business apps with custom intelligence powered by Semantic Kernel and local/cloud vector search.

- `POST /api/ai/chat`: Send a natural language query with automatic context retrieval.
  - **Request Body:**
    ```json
    {
      "message": "What is the total revenue for Q3 in warehouse Alpha?"
    }
    ```

---

## 📞 Developer Support
- **Technical Lead:** Mostafa Elnagar (`saskw2010`)
- **Support Portal:** [wytsky.com/contact](https://wytsky.com)
- **Repository:** [Sky365-Engineering-Knowledge-Base](https://github.com/saskw2010/Sky365-Engineering-Knowledge-Base)
