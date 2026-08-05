# Documentation Synchronization Workflow

## Trigger

Run this workflow whenever a task changes behavior, contracts, architecture, data, security, deployment, operations, or project status.

## Steps

1. Identify documents affected by the change.
2. Compare implementation with existing documentation.
3. Update factual current-state documents.
4. Create or update ADRs for architectural decisions.
5. Update `PROJECT-STATUS.md`.
6. Update `CHECKPOINT.md` with completed work, verification evidence, unresolved risks, and next action.
7. Update changelog or release notes when applicable.
8. Confirm no proposed behavior is presented as implemented behavior.

## Minimum checkpoint content

- Date.
- Task or change reference.
- Work completed.
- Files or modules changed.
- Verification performed.
- Verification not performed.
- Open risks and unknowns.
- Exact recommended next step.

## Drift rule

When documentation is stale, do not silently rewrite history. Mark the old statement as obsolete or explain the correction and evidence.
