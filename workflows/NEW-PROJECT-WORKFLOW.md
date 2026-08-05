# New Project Workflow

## Objective

Prevent implementation from starting before the product, domain, constraints, and delivery model are understood.

## Phase 1 — Product discovery

Create:

- `README.md`;
- `docs/product/PRODUCT-BRIEF.md`;
- `docs/product/PERSONAS.md`;
- `docs/product/USER-STORIES.md`;
- `docs/product/NON-GOALS.md`;
- `docs/product/CONSTRAINTS.md`;
- `docs/product/ACCEPTANCE-CRITERIA.md`.

## Phase 2 — Domain and architecture

Create:

- `docs/domain/DOMAIN-MODEL.md`;
- `docs/domain/GLOSSARY.md`;
- `docs/architecture/ARCHITECTURE.md`;
- `docs/architecture/SYSTEM-CONTEXT.md`;
- `docs/data/DATA-MODEL.md`;
- `docs/api/API-CONTRACTS.md`;
- `docs/security/SECURITY-MODEL.md`;
- `docs/architecture/TENANCY-MODEL.md` when SaaS or multi-tenant.

## Phase 3 — Delivery plan

Create:

- `PROJECT-STATUS.md`;
- `CHECKPOINT.md`;
- `docs/execution/IMPLEMENTATION-PLAN.md`;
- `docs/execution/RISK-REGISTER.md`;
- `docs/testing/TEST-STRATEGY.md`;
- `docs/operations/DEPLOYMENT.md`;
- `docs/operations/ROLLBACK.md`.

## Gate before coding

Do not begin production implementation until:

- the initial scope is explicit;
- non-goals are documented;
- critical assumptions are visible;
- architecture and data boundaries are reviewed;
- first-phase acceptance criteria exist;
- implementation is divided into safe increments.

## First implementation rule

Implement the smallest vertical slice that validates the architecture and user value. Do not scaffold the entire imagined platform before testing the core path.
