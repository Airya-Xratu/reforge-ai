---
name: product-analyst
description: >
  Product Manager lens. Reconstructs product purpose, target users, personas,
  jobs-to-be-done, feature hierarchy, business goals, opportunities, and Product DNA
  from code evidence.
---

# Purpose

Understand what the product is, who it serves, and what makes it unique.

# When This Skill Activates

- User asks "what is this app?" or "what does this product do?"
- Part of UNDERSTAND, REDESIGN, or REBUILD workflows
- After feature-mapper has identified features

# Inputs

- `project_model.features`
- `project_model.screens`
- `project_model.api_contracts`
- `project_model.data_models`
- `project_model.fingerprint`

# Responsibilities

1. Infer product purpose from features, models, and APIs
2. Reconstruct target users and personas
3. Map jobs-to-be-done to features
4. Classify features as core, secondary, or nice-to-have
5. Infer business goals from monetization and analytics patterns
6. Extract Product DNA — characteristics that must survive redesign
7. Identify product risks and opportunities

# Evidence It Should Collect

- Feature purpose from screen and API evidence (MEDIUM confidence)
- User personas from feature complexity and data types (LOW-MEDIUM confidence)
- Product DNA from interaction patterns and design decisions (MEDIUM confidence)
- Business goals from monetization patterns (LOW-MEDIUM confidence)
- Product risks from architecture gaps (MEDIUM confidence)

# Analysis Method

1. Review feature map from feature-mapper
2. Analyze data models to infer domain
3. Review API contracts for backend scope
4. Infer user types from feature complexity
5. Map features to user jobs
6. Extract Product DNA from consistent patterns
7. Identify gaps and risks

# Expected Output

- `project_model.product` — purpose, users, personas, JTBD, goals, risks
- `project_model.product_dna` — characteristics that define the product

# Confidence Rules

- Product purpose: MEDIUM (inferred from features)
- Personas: LOW-MEDIUM (inferred from feature complexity)
- Product DNA: MEDIUM (inferred from consistent patterns)
- Business goals: LOW-MEDIUM (inferred from monetization signals)

# What This Skill Must Not Do

- Do not present inferences as facts
- Do not make market analysis claims
- Do not modify analyzed project
- Do not evaluate code quality

# Related Skills

- feature-mapper (provides feature data)
- ux-analyst (provides UX patterns for DNA extraction)
- redesign-planner (uses product analysis for redesign)
