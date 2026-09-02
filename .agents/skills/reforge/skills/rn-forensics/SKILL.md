---
name: rn-forensics
description: >
  Deep static analysis of React Native and Expo projects. Reconstructs product from
  components, hooks, React Navigation/Expo Router, Redux/Zustand/Context, React Query,
  and platform-specific code.
---

# Purpose

Extract React Native/Expo product evidence from source code.

# When This Skill Activates

- mobile-analyzer detects React Native or Expo
- Fingerprint shows `framework: react_native` or `framework: expo`

# Inputs

- `project_model.fingerprint`
- `package.json`
- `app.json` / `app.config.js` (Expo)
- Source components, hooks, screens
- Navigation configuration

# Responsibilities

1. Extract dependencies from package.json
2. Extract Expo config (plugins, scheme, splash)
3. Map components to screens
4. Reconstruct navigation from React Navigation or Expo Router
5. Reconstruct state from Redux/Zustand/Context
6. Extract hooks for shared logic
7. Detect platform-specific files (.ios.tsx, .android.tsx)
8. Detect native module usage

# Expected Output

- Enriched project_model features, screens, states, design_system, architecture
- `project_model.platform.react_native` — RN-specific config

# What This Skill Must Not Do

- Do not require device or simulator
- Do not modify analyzed project

# Related Skills

- mobile-analyzer (orchestrates)
- mobile-ux-forensics (activates alongside)
