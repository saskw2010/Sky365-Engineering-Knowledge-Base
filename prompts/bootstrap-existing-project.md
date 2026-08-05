# Bootstrap an Existing Project

Read the Sky365 Engineering Knowledge Base and apply its existing-project discovery workflow to the explicitly named target repository.

## Safety

- Work only in the named repository.
- Use a dedicated branch.
- Do not refactor or modify production behavior during discovery.
- Do not merge automatically.

## Instructions

1. Inspect repository structure, project files, dependencies, configuration, schemas, APIs, tests, deployment artifacts, security boundaries, background tasks, and integrations.
2. Produce an evidence-based As-Is system map.
3. Create or update:
   - `AGENTS.md`
   - `PROJECT-STATUS.md`
   - `CHECKPOINT.md`
   - `docs/INDEX.md`
   - `docs/discovery/CURRENT-SYSTEM-ASSESSMENT.md`
   - `docs/discovery/CODEBASE-INVENTORY.md`
   - `docs/discovery/DEPENDENCY-INVENTORY.md`
   - `docs/discovery/UNKNOWN-AREAS.md`
   - `docs/discovery/TECH-DEBT-REGISTER.md`
   - `docs/maps/PROJECT-MIND-MAP.md`
   - `docs/maps/MODULE-DEPENDENCY-GRAPH.md`
   - `docs/architecture/AS-IS-ARCHITECTURE.md`
   - `docs/execution/RISK-REGISTER.md`
4. Mark information as verified, inferred, proposed, obsolete, or unknown.
5. Identify contradictions between code and documentation.
6. Stop after discovery documentation and open a Pull Request for review.
