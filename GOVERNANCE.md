# Governance

## Repository role

This repository is the central control plane for engineering knowledge and agent behavior across Sky365 projects.

It defines shared policy. It does not replace project-local truth.

## Governance principles

1. Every governed project remains an independent repository.
2. Project-specific documentation stays beside the project code.
3. Shared standards, templates, playbooks, and terminology stay here.
4. Adoption is explicit and repository-by-repository.
5. Existing running projects begin with discovery, not redesign.
6. All architectural changes require traceable decisions.
7. Documentation maintenance is part of the Definition of Done.

## Change classes

### Reversible decisions

Examples: UI libraries, local utilities, internal formatting choices.

These may be changed through normal Pull Requests when risk is low.

### Costly or difficult-to-reverse decisions

Examples: tenancy model, database strategy, identity model, public API contracts, event schemas, security boundaries, integration protocols.

These require an ADR and explicit review.

## Project adoption process

1. Register the project in `PROJECT-REGISTRY.md`.
2. Classify it as active product, active component, research, prototype, legacy, duplicate, archive candidate, or unknown.
3. Select the correct workflow.
4. Create a dedicated adoption branch in the target repository.
5. Perform discovery and documentation only.
6. Open a Pull Request for review.
7. Begin implementation only after the current-state map is accepted.

## Authority boundaries

Agents may draft, inspect, document, plan, test, and create Pull Requests within explicit scope.

Agents must not:

- modify unnamed repositories;
- merge without instruction;
- rotate credentials;
- change production infrastructure;
- alter customer data;
- publish private information;
- infer approval from silence.
