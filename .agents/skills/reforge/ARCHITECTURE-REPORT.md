# Reforge v2.0 — Architecture Report

## What Changed

### Critical Fixes

| # | Problem | Fix | Impact |
|---|---|---|---|
| 1 | No shared project model | Created `project-model.yaml` — 20-section canonical schema | All sub-skills now compose. Findings flow between phases. |
| 2 | Parent SKILL.md too long (143 lines) | Rewrote to 102 lines with output mode routing | Agent loads 29% less context before starting work. |
| 3 | No output modes | Added 10 output modes (ANALYZE, RECONSTRUCT, REDESIGN, etc.) | Agent knows exactly which sub-skills to activate. |
| 4 | No decision traceability | Added `decision-logger` sub-skill + decision_log section | Every recommendation has reasoning, evidence, alternatives. |
| 5 | No human override | Added overrides section + override mechanism | User preferences override recommendations, recorded. |
| 6 | No incremental analysis | Added incremental mode to parent SKILL.md | Can analyze one screen/feature without full pipeline. |

### New Capabilities

| Capability | Implementation |
|---|---|
| **Shared Project Model** | 20-section YAML schema. All sub-skills read/write it. |
| **Output Modes** | 10 modes with explicit sub-skill routing table. |
| **Decision Log** | Decisions with reasoning, evidence, alternatives, tradeoffs, confidence. |
| **Human Override** | Override mechanism with reason tracking. Overrides persist across recommendations. |
| **Project Health** | 8-dimension scoring with evidence. No arbitrary numbers. |
| **Git History Evidence** | `git-analyzer` script extracts recent changes, churn, abandoned branches. |
| **Incremental Analysis** | Phase 0 only + relevant domain sub-skill for scoped requests. |
| **Idempotency Controls** | Sort outputs deterministically, cache in project_model. |

### Updated Sub-Skills (22 total, up from 20)

| Sub-Skill | Change |
|---|---|
| project-archaeologist | Added git history phase, project model writes |
| feature-mapper | Reads fingerprint, writes to project model |
| screen-analyzer | Reads features, writes to project model |
| state-analyzer | Reads screens, writes to project model |
| architecture-analyzer | Reads fingerprint, writes data models + API contracts |
| ux-analyst | Reads features/screens/states, writes to project model |
| ui-analyst | Reads screens, writes design system to project model |
| product-analyst | Reads features/screens/APIs, writes product + DNA |
| design-system-extractor | Writes to project model with evidence classification |
| mobile-analyzer | Writes permissions to project model |
| impact-analyzer | Reads all project model sections for blast radius |
| documentation-generator | Reads full project model for handoff |
| boilerplate-generator | Reads project model for MAS generation |
| minimum-viable-clone | Reads project model for MVC generation |
| feature-planner | Reads project model for context-aware planning |
| implementation-planner | Reads project model for context-aware planning |
| test-planner | Reads project model for test strategy |
| redesign-planner | Reads project model for current state |
| reference-analyzer | Reads project model for inspiration analysis |
| visual-forensics | Reads design system for code-visual comparison |
| **project-health** | NEW — 8-dimension scoring with evidence |
| **decision-logger** | NEW — Decision recording with reasoning |

### New Scripts

| Script | Purpose |
|---|---|
| git-analyzer | Extract git history as evidence (recent changes, churn, branches) |

### New Templates

| Template | Purpose |
|---|---|
| project-model.yaml | Shared contract schema (20 sections) |

### New Examples

| Example | Purpose |
|---|---|
| flutter-app-project-model.yaml | Complete project model excerpt showing all sections |

### File Count

| Category | v1.0 | v2.0 |
|---|---|---|
| Parent SKILL.md | 1 | 1 |
| Sub-skills | 20 | 22 |
| Templates | 10 | 11 |
| Scripts | 5 | 6 |
| Examples | 4 | 5 |
| **Total** | **40** | **45** |

## Weaknesses Still Present

| Weakness | Severity | Status | Reason |
|---|---|---|---|
| No runtime validation | MEDIUM | Deferred | Requires executing analyzed project |
| No cross-project comparison | LOW | Deferred | Out of scope for v2.0 |
| Template alignment incomplete | LOW | Partial | Some templates not fully aligned with project_model |
| Idempotency not tested | MEDIUM | Deferred | Requires real project testing |
| No skill versioning | LOW | Deferred | Framework limitation |

## What Each Review Criterion Found

### 1. Skill Loading
- **Before:** 143-line parent, no routing, agent loads everything
- **After:** 102-line parent, 10 output modes, explicit sub-skill routing

### 2. Reasoning Quality
- **Before:** Inconsistent evidence handling across sub-skills
- **After:** Shared project_model mandates evidence format. Decision log records reasoning.

### 3. Mobile Analysis
- **Before:** General guidance, no git history
- **After:** Git analyzer for evolution evidence. Sub-skills reference shared model.

### 4. Product Reconstruction
- **Before:** Sub-skills operated in isolation
- **After:** Product analyst reads features + screens + APIs from shared model.

### 5. UX Reconstruction
- **Before:** No shared state between UX and other lenses
- **After:** UX analyst reads features, screens, state machines from shared model.

### 6. UI Reconstruction
- **Before:** No observed/inferred/recommended distinction enforced
- **After:** Design system extractor mandates classification in evidence.

### 7. Reference Analysis
- **Before:** Generic guidance
- **After:** Reads project_model DNA section for preservation decisions.

### 8. Boilerplate
- **Before:** Generic generation instructions
- **After:** Reads architecture, design system, navigation from project model.

### 9. Agent Handoff
- **Before:** Standalone template, no project model link
- **After:** Template references project_model.yaml as source of truth.

### 10. Deterministic Tooling
- **Before:** 5 scripts
- **After:** 6 scripts (added git-analyzer). All executable.
