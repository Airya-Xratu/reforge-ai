---
name: ux-analyst
description: >
  UX researcher lens. Reconstructs information architecture, navigation, user journeys,
  workflows, interaction patterns, accessibility, and edge-case handling from static code.
---

# Purpose

Understand how users interact with the product.

# When This Skill Activates

- User asks about UX, user journeys, navigation, interactions
- Part of UNDERSTAND, REDESIGN workflows
- After screens and states are documented

# Inputs

- `project_model.features`
- `project_model.screens`
- `project_model.state_machines`
- `project_model.navigation`

# Responsibilities

1. Map information architecture from navigation and screen hierarchy
2. Reconstruct user journeys from code flow
3. Catalog interaction patterns (gestures, modals, forms)
4. Verify error, loading, empty, offline states
5. Evaluate accessibility (labels, hints, contrast, targets)
6. Identify friction points and cognitive load
7. Detect keyboard and gesture behavior (mobile)

# Evidence It Should Collect

- Navigation graph from route definitions (HIGH confidence)
- User journeys from screen flow (MEDIUM confidence)
- Interaction patterns from gesture handlers (HIGH confidence)
- State coverage from state machines (HIGH confidence)
- Accessibility from semantic labels (HIGH confidence)
- Friction from step counts and decision density (MEDIUM confidence)

# Analysis Method

1. Review navigation graph from feature-mapper
2. Trace code flow to reconstruct journeys
3. Scan for gesture handlers, modals, dialogs
4. Cross-reference screens with state machines for coverage
5. Check for accessibility labels and hints
6. Count steps for core tasks

# Expected Output

- `project_model.ux` — info architecture, journeys, interactions, accessibility, friction

# Confidence Rules

- Navigation graph: HIGH (from route definitions)
- Interaction patterns: HIGH (from gesture code)
- State coverage: HIGH (from state machine analysis)
- Journey reconstruction: MEDIUM (requires tracing)
- Accessibility: HIGH (observable from labels)
- Friction assessment: LOW-MEDIUM (subjective)

# What This Skill Must Not Do

- Do not evaluate visual design (that's ui-analyst)
- Do not analyze business logic
- Do not modify analyzed project

# Related Skills

- screen-analyzer (provides screen data)
- state-analyzer (provides state coverage)
- mobile-ux-forensics (mobile-specific UX patterns)
- ui-analyst (visual design analysis)
