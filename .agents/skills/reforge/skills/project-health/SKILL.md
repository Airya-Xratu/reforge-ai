---
name: project-health
description: >
  Scores project health across 8 dimensions with evidence: architecture, product,
  UX, UI, maintainability, testability, documentation, consistency.
---

# Purpose

Provide a quality baseline with evidence-backed scores.

# When This Skill Activates

- User asks about health, quality, score, technical debt
- Part of HEALTH, UNDERSTAND workflows

# Inputs

- `project_model` (all sections)

# Responsibilities

1. Score architecture health (module boundaries, dependency direction)
2. Score product health (feature completeness, coherence)
3. Score UX health (error/empty/loading states, accessibility)
4. Score UI health (design system usage, consistency)
5. Score maintainability (duplication, naming, TODOs)
6. Score testability (coverage, mocking, organization)
7. Score documentation (README, API docs, code comments)
8. Score consistency (naming, structure, patterns)
9. Every score must have evidence

# Expected Output

- `project_model.health` — 8-dimension scores with evidence

# Confidence Rules

- Scores are MEDIUM confidence (require interpretation)
- Evidence must be HIGH confidence (observable facts)

# What This Skill Must Not Do

- Do not produce arbitrary numbers without evidence
- Do not modify analyzed project

# Related Skills

- architecture-analyzer (provides architecture evidence)
- project-archaeologist (provides dead code/contradictions)
