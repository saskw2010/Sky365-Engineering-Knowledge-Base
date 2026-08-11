# Storage → GitHub → Career Evidence Audit

This folder is the permanent knowledge index for the long engineering session that started as a digital-storage cleanup exercise and evolved into a broader GitHub governance, DevSecOps, repository inventory, career-evidence and CV strategy initiative.

## Why this folder exists

The work documented in this session spans multiple repositories, technologies and engineering disciplines. It should not be stored inside an individual product repository such as SKY365, a Blazor application or an AI project. This folder keeps the session as cross-project engineering knowledge and career evidence.

## Scope

### 01. Storage Modernization
- Disk inventory and file classification.
- Separation of disposable installers from valuable source code, documents and family media.
- Family photo/video archive organization by media type and year.
- APK rescue, analysis and deduplication.
- Cleanup of generated build artifacts such as `bin`, `obj`, `.vs`, `node_modules` and `TestResults`.
- Compressed-archive inventory and duplicate/unique archive triage.

### 02. Project Portfolio Recovery
- Discovery of legacy and current source-code projects.
- Classification by technology: .NET, Blazor, CodeOnTime VB/C#, mobile, Python/AI, frontend and cloud/DevOps.
- Identification of duplicate project copies and likely newer/older versions.
- Long-term plan for comparing additional hard drives against the existing project inventory.

### 03. GitHub Inventory & Synchronization
- Local Git repository discovery.
- Comparison between local repositories and GitHub repositories.
- Identification of projects already on GitHub and previously unlinked project treasures.
- Safe branch-based preservation strategy for local variants before deciding the canonical version.
- Private-first upload strategy for projects requiring security review.

### 04. DevSecOps & Repository Governance
- Public / private / archived repository classification.
- Zombie-repository identification.
- Dependabot/security-alert enablement strategy.
- Archived-repository legacy notices.
- Sensitive-customer repository privacy review.
- Asset/logo scrubbing and Sky365 placeholder strategy for sensitive projects.
- Long-term GitHub/local-disk mirror and repository hygiene plan.

### 05. Documentation Automation
- README generation for repositories missing documentation.
- AI/Copilot-oriented plan to inspect repository structure and create evidence-based README files.
- Public portfolio/landing-page concept that publishes safe project documentation while source repositories may remain private.
- GitHub Actions auto-sync concept for keeping public portfolio documentation current.

### 06. Career Evidence Audit
- Repository evidence audit across AI, data science, full-stack engineering, software/solution architecture, ERP/SaaS, cloud/DevOps, integrations, automation and engineering leadership.
- Evidence-based professional-title assessment.
- Project inventory and technology-skills matrix.
- CV-variant strategy rather than forcing 20+ years of multidisciplinary work into one role label.

## Career-Audit Deliverables

The planned/generated evidence set is organized around the following documents:

1. `01-REPOSITORY-EVIDENCE-MAP.md`
2. `02-PROJECT-INVENTORY.md`
3. `03-TECHNOLOGY-SKILLS-MATRIX.md`
4. `04-PROFESSIONAL-TITLE-ASSESSMENT.md`
5. `05-CV-VARIANTS-STRATEGY.md`
6. `06-MICROSOFT-DATA-SCIENTIST-GAP-ANALYSIS.md`

Recommended permanent location:

```text
docs/career-evidence/
├── session-history/
│   └── 2026-storage-github-career-audit/
│       └── README.md
├── career-audit/
│   ├── 01-REPOSITORY-EVIDENCE-MAP.md
│   ├── 02-PROJECT-INVENTORY.md
│   ├── 03-TECHNOLOGY-SKILLS-MATRIX.md
│   ├── 04-PROFESSIONAL-TITLE-ASSESSMENT.md
│   ├── 05-CV-VARIANTS-STRATEGY.md
│   └── 06-MICROSOFT-DATA-SCIENTIST-GAP-ANALYSIS.md
├── devsecops/
├── github-governance/
└── cv-strategy/
```

## CV Architecture

Use one evidence source and derive multiple targeted CVs from it:

- **MASTER CV** — complete career record; source of truth, not the primary application document.
- **AI / LLM / Agentic AI CV** — LLMs, RAG, agents, fine-tuning, document intelligence, AI engineering and MLOps.
- **Principal Software / Solution Architect CV** — full-stack, .NET, Blazor, SaaS/ERP, system architecture, integrations and cloud delivery.
- **Microsoft / Enterprise AI Technical Specialist CV** — Azure, LLMs, Generative AI, ML/Data Science and enterprise customer transformation.
- **Engineering Leadership CV** — product/platform ownership, engineering management, architecture governance, release strategy and technical leadership.

DevOps/Cloud is a cross-cutting capability: it supports Solution Architecture directly, becomes MLOps/AI Platform Engineering in the AI CV, and supports governance/release management in the Engineering Leadership CV.

## Evidence Rule

Never turn a repository observation into a CV claim without classifying it as one of:

- **Directly proven** by source code, configuration, documentation, commits or repository metadata.
- **Strongly inferred** from implementation evidence.
- **Claimed elsewhere but not yet repository-proven.**

This prevents repository recency bias from rewriting the career history as if the work began with AI. The intended progression is:

`Software Engineer → Senior/Lead Engineer → Full-Stack & Enterprise Architecture → Product/Platform Engineering → Cloud/DevOps → AI/Data/LLM/Agentic Systems → Principal-level multidisciplinary technology leadership`

## Source Session

Original conversation export: `Organizing Digital Storage Assets.md`.

The source session is a historical evidence artifact. It contains planning, scripts, decisions, results, corrections and later career-audit work. Treat it as session history rather than polished technical documentation; extract durable decisions into the dedicated folders above.

## Next Consolidation Steps

- Import the full original session export as an immutable source artifact.
- Import the six generated career-audit reports.
- Build `MASTER-CAREER-PROFILE.md` as the single source of truth for CV generation.
- Link GitHub project evidence to career claims.
- Generate ATS variants from the master profile rather than maintaining disconnected CV copies.
