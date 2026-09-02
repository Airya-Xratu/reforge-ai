---
name: design-system-extractor
description: >
  Extracts design system from code: colors, typography, spacing, component tokens,
  theme configuration, and reusable patterns. Classifies as OBSERVED, INFERRED, or RECOMMENDED.
---

# Purpose

Document the visual language of the product.

# When This Skill Activates

- User asks about design system, theme, colors, typography
- Part of UNDERSTAND, REDESIGN, REBUILD workflows
- After UI analysis is initiated

# Inputs

- Theme/style configuration files
- Component files
- `project_model.fingerprint`

# Responsibilities

1. Extract color palette from theme files
2. Extract typography scale from text styles
3. Extract spacing system from constants
4. Extract border radius and elevation
5. Catalog component system with variants and states
6. Classify each finding as OBSERVED, INFERRED, or RECOMMENDED
7. Detect icon system and imagery patterns

# Evidence It Should Collect

- Color values from theme (HIGH confidence)
- Typography scale (HIGH confidence)
- Spacing constants (HIGH confidence)
- Component variants (HIGH confidence)
- Dark mode tokens (HIGH confidence)

# Analysis Method

1. Locate theme configuration
2. Extract all design tokens
3. Scan components for token usage
4. Detect hardcoded values (potential missing tokens)
5. Classify each finding

# Expected Output

- `project_model.design_system` — complete design token inventory

# Confidence Rules

- Token values: HIGH (hardcoded in theme)
- Token usage: HIGH (observable from imports)
- Missing tokens: MEDIUM (inferred from hardcoded values)
- Component states: HIGH (observable from code)

# What This Skill Must Not Do

- Do not evaluate design quality
- Do not modify analyzed project

# Related Skills

- ui-analyst (provides visual analysis)
- visual-forensics (screenshot comparison)
- boilerplate-generator (uses design system for MAS)
