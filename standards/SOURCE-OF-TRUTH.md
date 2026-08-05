# Source of Truth

## Priority order

When sources conflict, use this order unless an approved ADR states otherwise:

1. Executable code and database schema.
2. Automated tests.
3. Configuration and deployment files.
4. Architecture Decision Records.
5. Current project documentation.
6. Legacy documentation.
7. Assumptions.

## Conflict handling

Do not silently choose one source and continue. Record:

- the conflicting sources;
- which source currently governs runtime behavior;
- business or operational risk;
- recommended resolution;
- responsible owner;
- target review date.

## Documentation labels

Every significant claim should be classifiable as:

- `verified` — supported by executable evidence;
- `inferred` — conclusion from incomplete evidence;
- `proposed` — future design, not current behavior;
- `obsolete` — no longer authoritative;
- `unknown` — evidence is insufficient.
