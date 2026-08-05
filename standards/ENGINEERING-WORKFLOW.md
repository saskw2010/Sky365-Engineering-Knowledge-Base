# Engineering Workflow

## Standard lifecycle

```text
Discover -> Map -> Document -> Decide -> Plan -> Implement -> Verify -> Update Memory
```

## Discover

Read governing standards and inspect the target repository. Identify project type, affected modules, business context, dependencies, tests, configuration, deployment artifacts, and data boundaries.

## Map

Create or update the As-Is system map, module map, dependency graph, data flow, integrations, and unknown areas.

## Document

Record verified facts separately from inferred or proposed information. Update status, risks, and constraints.

## Decide

Identify whether the task requires a reversible implementation choice or an architectural decision. Create an ADR for costly or difficult-to-reverse decisions.

## Plan

Define the smallest safe change, affected files, migration impact, tests, rollback approach, and documentation updates.

## Implement

Keep the change scoped. Avoid unrelated refactoring. Preserve compatibility unless a breaking change is explicitly approved.

## Verify

Run relevant build, tests, static analysis, migration validation, security checks, and manual acceptance steps. Record actual evidence.

## Update memory

Update:

- `PROJECT-STATUS.md`;
- `CHECKPOINT.md`;
- affected documentation;
- ADRs;
- changelog or release notes where applicable;
- project registry state when adoption status changes.

## Stop conditions

Stop and request review when:

- business rules are ambiguous;
- documentation conflicts with executable behavior;
- secrets or production data would be exposed;
- a migration is destructive;
- scope expands materially;
- required tests cannot be executed;
- an architectural decision has no approved direction.
