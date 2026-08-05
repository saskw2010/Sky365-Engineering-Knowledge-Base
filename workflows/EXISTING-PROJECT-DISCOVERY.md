# Existing Project Discovery Workflow

## Objective

Create an evidence-based As-Is model of a running or legacy repository without changing production behavior.

## Discovery-only rule

During this phase:

- do not refactor production code;
- do not replace frameworks or databases;
- do not rewrite modules from preference;
- do not treat missing documentation as permission to invent behavior.

## Inspection scope

Inspect, where present:

- repository structure and project files;
- runtime and package dependencies;
- application entry points;
- modules and boundaries;
- database schemas, migrations, procedures, and seeds;
- APIs, events, queues, tools, and external integrations;
- authentication, authorization, tenancy, and secrets handling;
- tests and testability;
- CI/CD, containers, infrastructure, and deployment configuration;
- observability, audit, background tasks, retries, and failure handling;
- Git history, issues, and Pull Requests when required to explain current behavior.

## Required outputs

Create or update:

```text
docs/INDEX.md
docs/discovery/CURRENT-SYSTEM-ASSESSMENT.md
docs/discovery/CODEBASE-INVENTORY.md
docs/discovery/DEPENDENCY-INVENTORY.md
docs/discovery/UNKNOWN-AREAS.md
docs/discovery/TECH-DEBT-REGISTER.md
docs/maps/PROJECT-MIND-MAP.md
docs/maps/MODULE-DEPENDENCY-GRAPH.md
docs/architecture/AS-IS-ARCHITECTURE.md
docs/execution/RISK-REGISTER.md
PROJECT-STATUS.md
CHECKPOINT.md
```

## Evidence labels

Every material statement must be marked or written so it is clear whether it is:

- verified;
- inferred;
- proposed;
- obsolete;
- unknown.

## Review gate

Stop after producing discovery documentation. Summarize contradictions, critical risks, unknown business rules, and recommended next steps. Do not begin broad refactoring until the As-Is map is reviewed.
