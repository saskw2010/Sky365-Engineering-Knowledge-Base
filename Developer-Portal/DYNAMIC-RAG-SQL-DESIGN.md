# Dynamic RAG + SQL Server Design

## Goal

Answer operational questions with current, permission-aware ERP data while using retrieval-augmented generation for policies, manuals and business context. The model must not receive unrestricted database access.

## Request flow

```text
User -> WhiteSky Web Chat
     -> AI API (.NET 8 / Semantic Kernel)
     -> intent + tenant + permission resolver
        -> semantic retriever (approved document index)
        -> structured facts service (allow-listed SQL views/procedures)
     -> evidence merger + citation builder
     -> grounded response with freshness metadata
```

## SQL contract

Expose read-only, parameterized views or stored procedures. A recommended contract is:

```sql
CREATE PROCEDURE ai.GetInventorySummary
  @TenantId uniqueidentifier,
  @WarehouseId uniqueidentifier = NULL,
  @AsOfDate date = NULL
AS
BEGIN
  SET NOCOUNT ON;
  -- Implementation must enforce tenant ownership and role scope.
  SELECT item_id, sku, warehouse_id, quantity_on_hand, reorder_point, as_of_utc
  FROM ai.vw_inventory_summary
  WHERE tenant_id = @TenantId
    AND (@WarehouseId IS NULL OR warehouse_id = @WarehouseId)
    AND (@AsOfDate IS NULL OR CAST(as_of_utc AS date) <= @AsOfDate);
END;
```

The application should call a named function such as `GetInventorySummary`, not compose SQL from model output. Each function should have an explicit JSON schema, maximum row count, timeout and redaction policy.

## Evidence envelope

The AI API should normalize every source into an evidence envelope:

```json
{
  "sourceType": "sql|document",
  "sourceId": "inventory-summary:warehouse-alpha:2026-08-17",
  "title": "Inventory summary",
  "tenantId": "tenant-id",
  "retrievedAtUtc": "2026-08-17T00:00:00Z",
  "freshnessSeconds": 300,
  "fields": ["sku", "quantity_on_hand", "reorder_point"],
  "content": "...",
  "permission": "inventory.read"
}
```

Responses should include citations or a short evidence section whenever the answer includes a factual business value. If no authorized evidence is available, the assistant should say so instead of guessing.

## Guardrails

| Control | Requirement |
|---|---|
| Tenant isolation | Apply tenant and user-scope filters in the database layer and again in the service layer. |
| Authorization | Map endpoint functions to explicit permissions such as `inventory.read` or `finance.read`. |
| Prompt injection | Treat retrieved documents as data; never allow document text to override system or authorization rules. |
| PII | Redact or aggregate employee, payroll and customer data unless the user has a justified permission. |
| Freshness | Return the data timestamp and reject stale sources for time-sensitive questions. |
| Cost and latency | Set token, row, timeout and retrieval-count limits; cache only permission-safe summaries. |
| Auditability | Log request ID, tenant, function, sources, policy decision and model version without storing secrets. |

## Evaluation set

Maintain test cases in both Arabic and English across finance, inventory, HR, POS, education and general support. Each case should define expected sources, acceptable answer facts, authorization scope and refusal behavior. Track retrieval recall, citation precision, groundedness, latency and unsafe-answer rate.

## Pilot checklist

- [ ] SQL functions are read-only, parameterized and tenant-filtered.
- [ ] Vector documents have tenant, language, effective date and access metadata.
- [ ] AI answers expose citations and timestamps.
- [ ] Unauthorized questions produce a safe refusal.
- [ ] Arabic and English golden questions pass evaluation thresholds.
- [ ] Logs and dashboards are available to operators.
- [ ] Secrets are stored outside source control and client bundles.
