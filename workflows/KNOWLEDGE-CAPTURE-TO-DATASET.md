# Knowledge Capture to Dataset Workflow

## Objective

Convert verified lessons from Sky365 engineering work into governed candidate learning records without disturbing the normal implementation workflow.

## Trigger

Run this workflow after a meaningful task, incident, design decision, debugging session, migration, evaluation, or repeated engineering loop produces knowledge that is likely reusable across projects.

Do not trigger it for trivial edits, unreviewed speculation, or ordinary generated text.

## Workflow

### 1. Detect a reusable lesson

Ask whether the work produced a transferable pattern, decision rule, failure mode, tool-use sequence, or validated input/output example.

### 2. Preserve project truth first

Update the target project's normal documentation, ADRs, status, checkpoint, tests, and code comments as required. Dataset capture must never replace project documentation.

### 3. Create a candidate record

Create:

`docs/learning/SKY-LRN-<number>-<slug>.md`

Use `training/LEARNING-RECORD-TEMPLATE.md` from the central Knowledge Base.

### 4. Link evidence

Reference exact files, tests, schemas, commits, issues, pull requests, official specifications, and authorized domain sources.

### 5. Generalize carefully

Remove irrelevant project-specific detail while preserving the constraints that made the lesson valid. Do not overgeneralize from a single case.

### 6. Redact and rights-check

Remove secrets, customer data, personal data, internal identifiers, and unlicensed third-party content. Record provenance and license status.

### 7. Validate

Confirm that the lesson matches the implemented and tested result. Mark unsupported parts as inferred, proposed, or unknown.

### 8. Submit for human review

Keep:

`training_approved: false`

An authorized reviewer decides whether the record may be promoted to the central Knowledge Base.

### 9. Normalize centrally

Approved records may be copied or transformed into:

`training/records/<domain>/`

They should be deduplicated, tagged, versioned, and assigned stable record identifiers.

### 10. Export separately

Dataset builders may later transform approved records into JSONL, preference pairs, tool traces, evaluation cases, or retrieval documents. Dataset export and model training are separate controlled operations.

## Agent completion report

When a candidate record is created, report:

- record path
- reusable lesson
- evidence state
- validation performed
- redactions applied
- licensing status
- unresolved risks
- required human reviewer

## Prohibition

Do not automatically scrape all repository activity into a dataset. High-volume low-quality capture creates noise, contamination, licensing risk, privacy risk, and misleading training signals.