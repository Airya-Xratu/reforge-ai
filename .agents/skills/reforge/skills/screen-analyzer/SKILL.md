---
name: screen-analyzer
description: >
  Comprehensive screen inventory. For each screen: purpose, components, data, actions,
  navigation, entry/exit points, and composition.
---

# Purpose

Catalog every screen and understand its role in the product.

# When This Skill Activates

- User asks about screens, pages, views
- Part of UNDERSTAND, REDESIGN, ADD_FEATURE workflows
- After features are mapped

# Inputs

- `project_model.features`
- `project_model.fingerprint`
- Screen/page/component files

# Responsibilities

1. Discover all screens from routes, navigation, widgets
2. Classify screens by function (navigation, content, creation, auth, utility)
3. Map entry and exit points per screen
4. Identify components per screen
5. Document data requirements per screen
6. Catalog actions per screen
7. Build screen relationship map

# Evidence It Should Collect

- Screen existence from route targets (HIGH confidence)
- Screen purpose from widget/component content (MEDIUM confidence)
- Components from widget tree analysis (HIGH confidence)
- Entry/exit from navigation code (HIGH confidence)
- Data requirements from state/props (HIGH confidence)

# Analysis Method

1. Discover screens from route definitions and navigation pushes
2. Classify by function
3. For each screen: trace entry points, exit points, components, data, actions
4. Build relationship map

# Expected Output

- `project_model.screens` — complete screen inventory

# Confidence Rules

- Screen existence: HIGH (from routes)
- Components: HIGH (from widget trees)
- Entry/exit points: HIGH (from navigation code)
- Purpose: MEDIUM (inferred from content)
- Data requirements: HIGH (from state/props)

# What This Skill Must Not Do

- Do not evaluate visual design
- Do not analyze business logic meaning
- Do not modify analyzed project

# Related Skills

- feature-mapper (provides feature context)
- state-analyzer (provides state details)
- ux-analyst (uses screens for journey analysis)
