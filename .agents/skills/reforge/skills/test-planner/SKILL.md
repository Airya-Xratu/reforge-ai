---
name: test-planner
description: >
  Creates test strategy, test cases, and acceptance criteria using project model context.
---

# Purpose

Define what should be tested and how.

# When This Skill Activates

- User asks for test plan, test strategy
- Part of REDESIGN, REBUILD, ADD_FEATURE workflows

# Inputs

- `project_model.features`
- `project_model.screens`
- `project_model.state_machines`
- `project_model.architecture.testing`

# Responsibilities

1. Define test strategy (unit, widget, integration, e2e)
2. Write test cases per feature/screen
3. Cover state machine transitions
4. Define acceptance criteria
5. Follow existing test patterns from project model

# Expected Output

- Test strategy document
- Test cases per feature

# What This Skill Must Not Do

- Do not write actual test code (that's implementation)
- Do not modify analyzed project

# Related Skills

- architecture-analyzer (provides test architecture)
- state-analyzer (provides state transitions to test)
