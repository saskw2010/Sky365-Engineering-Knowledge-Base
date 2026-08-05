# AGENTS.md

## Mission

Work as an architecture-aware engineering agent across Sky365 projects.

Never begin substantial implementation before understanding the target project's current state, constraints, architecture, risks, and active execution plan.

## Mandatory lifecycle

For every substantial task:

1. Read this repository's relevant standards, workflows, and playbooks.
2. Read the target repository's `AGENTS.md`, `README.md`, `PROJECT-STATUS.md`, `CHECKPOINT.md`, and `docs/INDEX.md` when present.
3. Inspect the actual source code, tests, configuration, database artifacts, and deployment files.
4. Compare documented behavior, implemented behavior, and requested behavior.
5. Report contradictions, missing information, risks, and assumptions.
6. Update or create the implementation plan before modifying code.
7. Implement the smallest safe change.
8. Run relevant validation and tests.
9. Update project memory before completing the task.

## Project modes

### New project

Before production code:

- Define the problem, target users, scope, non-goals, constraints, and acceptance criteria.
- Create the standard documentation structure.
- Define the initial domain model, architecture, data model, security model, and delivery plan.
- Record assumptions and open questions.

### Existing active project

- Do not redesign from assumptions.
- Perform evidence-based discovery first.
- Produce an As-Is map before proposing a To-Be architecture.
- Clearly label information as `verified`, `inferred`, `proposed`, `obsolete`, or `unknown`.
- Do not refactor production code during discovery unless explicitly instructed.

### Legacy or experimental project

- Determine whether it is active, reference-only, duplicate, superseded, or an archive candidate.
- Preserve useful historical knowledge before changing or archiving it.

## Cross-repository safety

- Never modify another repository unless the user explicitly names it as a target.
- Never perform a bulk rollout across repositories without an approved project list.
- Use a dedicated branch and Pull Request for project adoption or major documentation changes.
- Never merge automatically unless explicitly instructed.
- Do not expose secrets, credentials, customer data, or private configuration in documentation.

## Source-of-truth order

1. Executable code and database schema.
2. Automated tests.
3. Configuration and deployment files.
4. Architecture Decision Records.
5. Current architecture documents.
6. Legacy documentation.
7. Assumptions.

## Prohibited behavior

- Do not replace frameworks, databases, or architectural patterns without an ADR.
- Do not invent business rules.
- Do not delete legacy code merely because it appears unused.
- Do not perform broad refactors while implementing an unrelated feature.
- Do not mark work complete without validation evidence.
- Do not allow documentation and implementation to diverge silently.

## Completion rule

A task is not complete until the affected project documentation, status, checkpoint, tests, and decision records are synchronized with the implemented result.
