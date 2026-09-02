---
name: mobile-ux-forensics
description: >
  Reconstructs mobile-specific UX from static code: gestures, keyboard behavior,
  safe areas, orientation, status bar, modals, haptics, permissions, biometrics,
  app lifecycle, deep links, notifications, share sheets, and system pickers.
---

# Purpose

Understand mobile-specific user interactions beyond screen navigation.

# When This Skill Activates

- mobile-analyzer activates (always alongside platform forensics)
- User asks about mobile gestures, interactions, lifecycle

# Inputs

- `project_model.screens`
- `project_model.state_machines`
- Gesture handler code
- Permission request code
- Lifecycle handler code

# Responsibilities

1. Catalog gestures per screen (swipe, long-press, pull-to-refresh, drag)
2. Analyze keyboard behavior (avoidance, dismiss, return key)
3. Detect safe area usage
4. Detect orientation handling
5. Detect status bar configuration
6. Catalog modal presentation patterns
7. Detect haptic feedback usage
8. Analyze permission flow (request → rationale → settings)
9. Detect biometric authentication flows
10. Analyze app lifecycle handling
11. Detect deep link patterns
12. Detect notification handling
13. Detect share sheets and system pickers
14. Build mobile journey model with gestures, decisions, interruptions, errors, recovery

# Expected Output

- `project_model.ux` (enriched with mobile patterns)
- `project_model.mobile_journeys` — rich journey model
- `project_model.mobile_gestures` — per-screen gesture inventory

# Confidence Rules

- Gesture detection: HIGH (from handler code)
- Permission flow: HIGH (from request code)
- Lifecycle handling: HIGH (from observer code)
- Journey reconstruction: MEDIUM (requires tracing)

# What This Skill Must Not Do

- Do not require device or emulator
- Do not modify analyzed project

# Related Skills

- mobile-analyzer (orchestrates alongside platform forensics)
- ux-analyst (general UX patterns)
