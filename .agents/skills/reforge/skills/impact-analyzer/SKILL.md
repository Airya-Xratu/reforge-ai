---
name: impact-analyzer
description: >
  Estimates blast radius of proposed changes. Maps affected features, screens,
  states, APIs, components, and dependencies.
---

# Purpose

Answer "what will break if I change this?"

# When This Skill Activates

- User asks about impact, blast radius, what will break
- Part of ADD_FEATURE, REDESIGN workflows
- After project model is built

# Inputs

- `project_model.features`
- `project_model.screens`
- `project_model.state_machines`
- `project_model.architecture`
- `project_model.design_system`

# Responsibilities

1. Identify direct impact of proposed change
2. Trace cascading dependencies via project model
3. Estimate test impact
4. Assess risk level
5. Recommend mitigation

# Expected Output

- Impact analysis with direct/cascading effects, risk level, mitigation

# Confidence Rules

- Direct impact: HIGH (traceable)
- Cascading impact: MEDIUM (may miss indirect paths)
- Risk assessment: MEDIUM (requires judgment)

# What This Skill Must Not Do

- Do not modify analyzed project

# Related Skills

- architecture-analyzer (provides dependency data)
- feature-mapper (provides feature dependencies)
