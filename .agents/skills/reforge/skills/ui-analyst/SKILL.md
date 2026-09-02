---
name: ui-analyst
description: >
  UI/visual designer lens. Extracts visual hierarchy, component structure, layout patterns,
  responsive behavior, and design system from code.
---

# Purpose

Understand the visual design and component architecture.

# When This Skill Activates

- User asks about UI, visual design, components, layout
- Part of UNDERSTAND, REDESIGN workflows
- After screens are documented

# Inputs

- `project_model.screens`
- `project_model.fingerprint`
- Theme files, style definitions, component files

# Responsibilities

1. Analyze visual hierarchy per screen
2. Extract typography from theme/style definitions
3. Extract color palette from theme constants
4. Extract spacing patterns
5. Catalog component inventory with states
6. Detect responsive behavior and breakpoints
7. Detect dark/light mode support
8. Classify findings as OBSERVED, INFERRED, or RECOMMENDED

# Evidence It Should Collect

- Color values from theme files (HIGH confidence)
- Typography scale from text styles (HIGH confidence)
- Spacing values from constants (HIGH confidence)
- Component reuse across screens (HIGH confidence)
- Dark mode support (HIGH confidence)
- Responsive breakpoints (HIGH confidence)

# Analysis Method

1. Locate theme/style configuration files
2. Extract color, typography, spacing tokens
3. Scan component files for variants and states
4. Check for responsive layouts and breakpoints
5. Verify dark mode theme definitions

# Expected Output

- `project_model.design_system` — colors, typography, spacing, components, responsive behavior

# Confidence Rules

- Color extraction: HIGH (hardcoded values)
- Typography: HIGH (defined in theme)
- Spacing: HIGH (constants or theme)
- Component inventory: HIGH (observable from files)
- Visual hierarchy: MEDIUM (requires interpretation)

# What This Skill Must Not Do

- Do not evaluate UX quality (that's ux-analyst)
- Do not analyze business logic
- Do not modify analyzed project

# Related Skills

- design-system-extractor (deep token extraction)
- visual-forensics (screenshot analysis)
- ux-analyst (UX patterns)
