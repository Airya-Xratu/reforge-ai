---
name: redesign-planner
description: >
  Plans a redesign: current state → problems → design principles → proposed product →
  UX → UI → architecture impact → migration strategy → implementation plan.
---

# Purpose

Create a structured redesign proposal without modifying code.

# When This Skill Activates

- User asks to "redesign", "rebuild", "overhaul"
- Part of REDESIGN workflow
- After project is understood

# Inputs

- `project_model` (all sections)
- `project_model.product_dna` (what must survive)

# Responsibilities

1. Document current state from project model
2. Categorize problems (product, UX, UI, engineering)
3. Propose design principles
4. Propose product changes (preserve, enhance, remove, add, simplify)
5. Propose UX improvements
6. Propose UI direction
7. Estimate architecture impact
8. Create migration strategy
9. Produce implementation plan

# Evidence It Should Collect

- Current state from project_model (HIGH confidence)
- Problems from contradictions and gaps (MEDIUM confidence)
- Impact from architecture analysis (MEDIUM confidence)

# Expected Output

- Redesign proposal document
- Decision log entries

# Confidence Rules

- Current state: HIGH (from project_model)
- Problem identification: MEDIUM (requires interpretation)
- Proposed changes: LOW-MEDIUM (recommendation, not fact)

# What This Skill Must Not Do

- Do not modify analyzed project
- Do not present recommendations as requirements

# Related Skills

- project-archaeologist (current state)
- reference-analyzer (inspiration analysis)
- implementation-planner (implementation plan)
