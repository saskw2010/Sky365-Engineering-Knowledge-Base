# Feature Development Playbook

## Inputs

- Feature request.
- Acceptance criteria.
- Affected modules and contracts.
- Current project status and checkpoint.

## Procedure

1. Read project memory and relevant architecture.
2. Inspect the existing implementation and tests.
3. Confirm scope, non-goals, dependencies, security, tenancy, data, and compatibility impact.
4. Create or update the implementation plan.
5. Add or update tests before or with implementation.
6. Implement the smallest complete vertical change.
7. Validate build, tests, contracts, migrations, security, and operations impact.
8. Synchronize documentation and checkpoint.

## Stop conditions

Stop when business rules are unclear, the feature requires an unapproved breaking change, destructive migration, new security boundary, or unresolved architectural decision.
