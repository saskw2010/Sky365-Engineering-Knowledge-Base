# Sky365 Engineering Knowledge Base (SEKB)

The central engineering brain for all Sky365 projects.

## Purpose

This repository defines the engineering standards, documentation workflows, architecture patterns, AI-agent operating rules, templates, playbooks, and shared technical knowledge used across independent Sky365 repositories.

It does **not** contain all production source code. Each project keeps its own code and project-specific documentation. This repository governs how those projects are discovered, documented, built, reviewed, and maintained.

## Core workflow

```text
Discover -> Map -> Document -> Decide -> Plan -> Implement -> Verify -> Update Memory
```

## Repository map

- `AGENTS.md` — operating constitution for Codex and other coding agents.
- `GOVERNANCE.md` — cross-repository governance and safety rules.
- `PROJECT-REGISTRY.md` — catalog of governed Sky365 projects.
- `standards/` — engineering and documentation standards.
- `workflows/` — workflows for new and existing projects.
- `playbooks/` — task-specific execution playbooks.
- `templates/` — standard project documents.
- `prompts/` — reusable bootstrap and execution prompts.
- `knowledge/` — reusable engineering knowledge.
- `brain/` — official glossary, ontology, concept graph, and semantic model.

## Source-of-truth principle

For any target project, use this priority order:

1. Executable code and database schema.
2. Automated tests.
3. Configuration and deployment files.
4. Architecture Decision Records.
5. Current architecture and project documentation.
6. Legacy documentation.
7. Explicitly marked assumptions.

## Scope

This knowledge base is intended for Codex, Claude Code, Gemini Code, other engineering agents, and human developers working on Sky365 and WytSky systems.
