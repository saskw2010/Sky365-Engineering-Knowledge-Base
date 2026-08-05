# Documentation Standard

## Required project files

Every governed project should contain:

```text
README.md
AGENTS.md
PROJECT-STATUS.md
CHECKPOINT.md
docs/
  INDEX.md
  product/
  discovery/
  architecture/
  domain/
  data/
  api/
  security/
  testing/
  operations/
  decisions/
  maps/
  execution/
```

Not every directory must contain documents on day one. Empty directories should not be committed; create them as needed.

## Required document metadata

Use front matter for project documents when practical:

```yaml
---
status: draft
truth-state: verified
owner: unassigned
last-reviewed: YYYY-MM-DD
source: code-inspection
---
```

Allowed truth states:

- `verified`
- `inferred`
- `proposed`
- `obsolete`
- `unknown`

## Existing-project rule

Documentation for a running project must begin with evidence-based discovery:

- repository inventory;
- runtime and dependency inventory;
- module map;
- API map;
- data and persistence map;
- integrations;
- deployment model;
- test coverage;
- risks, unknowns, contradictions, and technical debt.

Separate **As-Is** from **To-Be**. Never overwrite current-state truth with a proposed architecture.

## New-project rule

Before production implementation, document:

- problem and opportunity;
- users and stakeholders;
- goals and non-goals;
- scope and constraints;
- acceptance criteria;
- domain model;
- architecture and data model;
- security and tenancy model;
- testing and deployment approach;
- implementation plan.

## Documentation synchronization

A change is incomplete when it alters behavior, contracts, architecture, deployment, security, data, or operational assumptions without updating the corresponding documents.

## Quality rules

- Prefer concise evidence over speculative prose.
- Link statements to code paths, schemas, tests, ADRs, or configurations.
- Mark uncertainty explicitly.
- Record dates and owners.
- Avoid duplicate sources of truth.
- Keep diagrams in Mermaid where possible so GitHub renders and versions them.
