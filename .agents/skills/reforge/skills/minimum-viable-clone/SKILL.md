---
name: minimum-viable-clone
description: >
  Generates Minimum Viable Clone (MVC) — smallest useful product experience
  with essential screens, core journey, mock data, and realistic UI.
---

# Purpose

Reconstruct the smallest version of the product that demonstrates its value.

# When This Skill Activates

- User asks for "minimum viable clone", "MVC", "prototype"
- Part of REBUILD workflow

# Inputs

- `project_model.features`
- `project_model.screens`
- `project_model.navigation`
- `project_model.design_system`
- `project_model.product_dna`

# Responsibilities

1. Select essential screens (8-15 from many)
2. Define core user journey
3. Create realistic mock data
4. Apply design system for realistic UI
5. Demonstrate key interaction states
6. Preserve Product DNA characteristics

# Expected Output

- Generated project files in `reforge/reconstruction/mvc/`

# What This Skill Must Not Do

- Do not include authentication, real APIs, complex state
- Do not modify analyzed project

# Related Skills

- boilerplate-generator (MAS = architecture, MVC = product experience)
- feature-mapper (selects essential features)
- screen-analyzer (selects essential screens)
