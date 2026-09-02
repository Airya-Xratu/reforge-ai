---
name: boilerplate-generator
description: >
  Generates Minimum Architectural Skeleton (MAS) — runnable project preserving
  architecture, navigation, design system, and state conventions without business logic.
---

# Purpose

Create the smallest runnable project that preserves architectural DNA.

# When This Skill Activates

- User asks for "minimal skeleton", "MAS", "scaffold"
- Part of BOILERPLATE workflow

# Inputs

- `project_model.fingerprint`
- `project_model.architecture`
- `project_model.design_system`
- `project_model.navigation`
- `project_model.state_machines`

# Responsibilities

1. Preserve same framework, structure, architecture pattern
2. Preserve same state management, DI, navigation
3. Preserve design system tokens
4. Create placeholder screens with navigation
5. Set up working state management
6. Remove all business logic, secrets, production data

# Expected Output

- Generated project files in `reforge/reconstruction/mas/`
- Decision log entries

# What This Skill Must Not Do

- Do not include business logic
- Do not include secrets or credentials
- Do not include production API calls
- Do not modify analyzed project

# Related Skills

- architecture-analyzer (provides architecture data)
- design-system-extractor (provides tokens)
- minimum-viable-clone (different: product experience vs architecture)
