---
name: reference-analyzer
description: >
  Analyzes a project as inspiration/reference. Separates generic patterns from
  product-specific behavior, implementation details, and distinctive patterns.
  Produces preserve/redesign/add/remove/simplify/modernize decisions.
---

# Purpose

Extract reusable product and design knowledge without cloning implementation.

# When This Skill Activates

- User asks to "use as reference" or "analyze as inspiration"
- Part of REFERENCE workflow
- After fingerprint is established

# Inputs

- `project_model` (all sections)

# Responsibilities

1. Classify findings as generic pattern, product-specific, implementation detail, branding, or distinctive
2. For each area: recommend preserve, redesign, add, remove, simplify, or modernize
3. Separate product architecture from implementation architecture
4. Ensure output describes an independently implementable product

# Evidence It Should Collect

- Pattern classification (generic vs product-specific) (MEDIUM confidence)
- Distinctive patterns (MEDIUM confidence)
- Implementation-specific behavior (HIGH confidence)

# Analysis Method

1. Review all project_model sections
2. Classify each finding
3. Produce clone→improve matrix
4. Verify independence test: could this be built from scratch?

# Expected Output

- Clone→improve matrix
- Preserved product knowledge
- Decision log entries

# Confidence Rules

- Generic pattern identification: MEDIUM
- Distinctive pattern identification: MEDIUM
- Implementation separation: HIGH

# What This Skill Must Not Do

- Do not blindly clone implementation
- Do not modify analyzed project

# Related Skills

- redesign-planner (uses reference analysis)
- product-analyst (provides product context)
