---
name: feature-mapper
description: >
  Discovers all features from code evidence, maps navigation graph, builds feature
  matrix, and reconstructs user-facing capabilities.
---

# Purpose

Identify what the product can do.

# When This Skill Activates

- User asks "what features does this have?"
- Part of UNDERSTAND, REDESIGN, ADD_FEATURE workflows
- After fingerprint is established

# Inputs

- `project_model.fingerprint`
- Route definitions
- Feature directories
- API endpoints
- Models and services
- Analytics events
- Permissions

# Responsibilities

1. Discover features from routes, directories, APIs, models
2. Classify features as core, secondary, nice-to-have, admin
3. Build feature matrix with evidence and confidence
4. Reconstruct navigation graph
5. Map feature dependencies
6. Identify dead feature indicators

# Evidence It Should Collect

- Features from route definitions (HIGH confidence)
- Features from directory structure (HIGH confidence)
- Features from API endpoints (HIGH confidence)
- Feature maturity from implementation completeness (MEDIUM confidence)
- Navigation from route config (HIGH confidence)
- Feature dependencies from imports (MEDIUM confidence)

# Analysis Method

1. Scan routes for discoverable features
2. Map feature directories
3. Extract API endpoints
4. Build feature matrix with evidence
5. Construct navigation graph
6. Map dependencies between features

# Expected Output

- `project_model.features` — complete feature inventory
- `project_model.navigation` — navigation graph

# Confidence Rules

- Feature existence: HIGH (from routes/directories)
- Feature maturity: MEDIUM (from implementation completeness)
- Feature value: LOW-MEDIUM (inferred from placement)
- Navigation graph: HIGH (from route definitions)

# What This Skill Must Not Do

- Do not evaluate feature quality
- Do not analyze visual design
- Do not modify analyzed project

# Related Skills

- screen-analyzer (provides screen details per feature)
- state-analyzer (provides state details per feature)
- product-analyst (uses features for product analysis)
