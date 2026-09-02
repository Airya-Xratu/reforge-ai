---
name: state-analyzer
description: >
  Reconstructs state machines for screens and features. Maps all states including
  happy path, error, loading, edge cases, and transitions.
---

# Purpose

Understand all possible states a screen or feature can be in.

# When This Skill Activates

- User asks about states, loading, error handling, edge cases
- Part of UNDERSTAND, REDESIGN, ADD_FEATURE workflows
- After screens are inventoried

# Inputs

- `project_model.screens`
- `project_model.fingerprint`
- State management code (BLoC, Provider, ViewModel, etc.)

# Responsibilities

1. Extract state models from state management code
2. Identify all states per screen (initial, loading, loaded, empty, error, etc.)
3. Map state transitions and triggers
4. Detect shared/global state
5. Identify edge cases and their handling
6. Rate coverage completeness

# Evidence It Should Collect

- State classes from code (HIGH confidence)
- Transitions from event/action handlers (HIGH confidence)
- Shared state from global providers/stores (HIGH confidence)
- Edge case handling from error callbacks (MEDIUM confidence)

# Analysis Method

1. Locate state management classes per screen
2. Extract state fields and transitions
3. Check for required states (loading, error, empty, offline)
4. Map shared state across screens
5. Identify edge cases and rate coverage

# Expected Output

- `project_model.state_machines` — state models per screen
- `project_model.shared_state` — global/feature state

# Confidence Rules

- State classes: HIGH (observable from code)
- Transitions: HIGH (from event handlers)
- Edge case handling: MEDIUM (may be implicit)
- Coverage assessment: MEDIUM (requires completeness check)

# What This Skill Must Not Do

- Do not evaluate UX quality
- Do not modify analyzed project

# Related Skills

- screen-analyzer (provides screen context)
- architecture-analyzer (provides state management approach)
- ux-analyst (uses states for UX analysis)
