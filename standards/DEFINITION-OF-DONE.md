# Definition of Done

A task is complete only when all applicable conditions are met.

## Functional

- Requested behavior is implemented.
- Acceptance criteria are satisfied.
- Error and edge cases are handled.

## Technical

- Build succeeds.
- Relevant automated tests pass.
- No unrelated refactoring is included.
- Backward compatibility impact is documented.
- Data migrations are validated and reversible where practical.

## Security and operations

- Secrets are not committed.
- Authorization and tenant boundaries are preserved.
- Logging, metrics, tracing, and audit requirements are addressed.
- Deployment and rollback impact are documented.

## Documentation

- `PROJECT-STATUS.md` is current.
- `CHECKPOINT.md` records the completed work and next action.
- Affected architecture, API, data, security, operations, and user-flow documents are synchronized.
- Significant decisions have an ADR.
- Known risks and unresolved questions remain visible.

## Evidence

The completion note or Pull Request must state:

- what changed;
- why it changed;
- how it was verified;
- what was not verified;
- remaining risks;
- documentation updated.
