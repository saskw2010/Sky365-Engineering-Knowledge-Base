# Learning Dataset Policy

## Purpose

Sky365 projects are not only software deliverables. They are also controlled sources of engineering knowledge that may later support internal evaluation, supervised fine-tuning, preference data, retrieval corpora, routing models, and domain-specific assistants.

The goal is to capture reusable knowledge from real work without copying secrets, customer data, proprietary third-party content, or unverified agent output into a training corpus.

## Core rule

Agents must separate normal project documentation from training-ready learning records.

Project documentation explains the current system.
Training records explain the reusable lesson, decision pattern, workflow, failure mode, or reasoning loop learned from the work.

Do not treat every chat, commit, log, or generated answer as training data.

## Capture candidates

Create a learning record when a task produces a reusable lesson such as:

- a verified architecture pattern
- a project-discovery method
- a successful implementation loop
- a failed approach and its correction
- a recurring debugging strategy
- a business-domain rule confirmed by an authorized source
- a tool-use or function-calling pattern
- an agent routing decision
- a documentation workflow
- an evaluation case
- a safety boundary
- a reusable prompt pattern
- a code transformation with clear input, output, and validation

## Required exclusions

Never place the following into a training dataset:

- credentials, tokens, secrets, private keys, connection strings, or internal endpoints
- customer-identifying data or production records
- personal data unless formally approved and lawfully processed
- source material whose license does not permit the intended use
- copied proprietary documentation
- unverified model claims
- hallucinated business rules
- raw chain-of-thought or hidden reasoning
- security-sensitive exploit instructions unrelated to approved defensive work
- generated code that was not reviewed or validated

## Evidence labels

Every learning record must use one of these evidence states:

- `verified`: confirmed by code, tests, schema, official documentation, or approved domain authority
- `inferred`: supported by evidence but not directly confirmed
- `proposed`: a recommendation not yet implemented
- `rejected`: attempted and intentionally not adopted
- `obsolete`: historically useful but no longer current
- `unknown`: unresolved

Only `verified` records may enter the default training-ready export.

## Rights and provenance

Every record must include:

- originating project
- source files or commits
- authoring agent or human reviewer
- external sources used
- license or permission status
- whether the content is original, adapted, summarized, or referenced
- review status

Public availability is not permission to train on or redistribute material.

## Human approval gate

Agents may create candidate learning records, but they must not mark them `training_approved: true`.

Only an authorized human reviewer may approve a record for dataset export.

## Storage model

Project-local candidates should be stored under:

`docs/learning/`

The central Knowledge Base should store normalized, reviewed patterns under:

`training/records/`

Dataset exports should be generated into a separate controlled location and should not be committed automatically.

## Quality requirements

A training-ready record must be:

- specific enough to reproduce the lesson
- independent of unnecessary project secrets
- validated against the actual implementation
- concise enough to avoid irrelevant context
- explicit about inputs, constraints, actions, outputs, and verification
- labeled by domain, task type, difficulty, tools, and failure modes

## Dataset use categories

Each approved record should declare one or more intended uses:

- `instruction_tuning`
- `tool_calling`
- `routing`
- `code_generation`
- `code_review`
- `debugging`
- `architecture_reasoning`
- `documentation`
- `retrieval_corpus`
- `evaluation_only`
- `preference_pair`

## Non-goal

This policy does not authorize automatic model training from all repository activity. It establishes a governed pipeline for producing high-quality candidate records that can later be reviewed, transformed, deduplicated, evaluated, and exported.