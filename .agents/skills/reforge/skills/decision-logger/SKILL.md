---
name: decision-logger
description: >
  Records non-obvious decisions with reasoning, evidence, alternatives, tradeoffs,
  and confidence. Supports human overrides.
---

# Purpose

Ensure every recommendation is traceable and overridable.

# When This Skill Activates

- Any skill makes a non-obvious recommendation
- User overrides a recommendation
- Part of all workflows (passive, always available)

# Responsibilities

1. Record decisions with: decision, reason, evidence, alternatives, tradeoffs, confidence
2. Record user overrides with reason
3. Ensure subsequent recommendations respect overrides
4. Never delete original recommendation when overridden

# Expected Output

- `project_model.decision_log` — decision entries
- `project_model.overrides` — user override entries

# What This Skill Must Not Do

- Do not log trivial/obvious decisions
- Do not override user decisions

# Related Skills

- All skills (passive capability, any skill can log decisions)
