---
name: implementation-planner
description: >
  Creates phased implementation plan with file plan, task ordering,
  dependency tracking, and acceptance criteria.
---

# Purpose

Turn analysis into an actionable build plan.

# When This Skill Activates

- User asks for implementation plan, build plan
- Part of REDESIGN, REBUILD, ADD_FEATURE workflows

# Inputs

- `project_model` (relevant sections)
- Analysis results from other skills

# Responsibilities

1. Order tasks by dependency
2. Group into phases
3. Create file plan (create/modify/delete)
4. Estimate effort per task
5. Assess risk per task
6. Define acceptance criteria per task

# Expected Output

- Phased implementation plan
- File plan

# What This Skill Must Not Do

- Do not implement anything
- Do not modify analyzed project

# Related Skills

- impact-analyzer (provides blast radius)
- test-planner (provides test plan)
