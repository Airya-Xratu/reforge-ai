---
name: mobile-analyzer
description: >
  Orchestrates mobile forensics. Detects platform (Flutter, Android, iOS, React Native),
  delegates to platform-specific forensics sub-skills, coordinates mobile UX analysis.
---

# Purpose

Detect the mobile platform and route to the correct forensic analysis pipeline.

# When This Skill Activates

- Project is detected as mobile (Flutter, Android, iOS, React Native, Expo)
- User asks to "analyze mobile project" or "analyze Flutter/Android/iOS app"
- project-archaeologist detects mobile framework in fingerprint

# Inputs

- `project_model.fingerprint` (from project-archaeologist)
- Project source code
- Platform-specific config files (pubspec.yaml, build.gradle, Info.plist, package.json)

# Responsibilities

1. Confirm platform detection from fingerprint
2. Load platform-specific forensics sub-skill
3. Load mobile-ux-forensics
4. Coordinate analysis between platform forensics and UX forensics
5. Collect permissions across platforms
6. Classify behaviors as product-level vs platform-specific
7. Validate completeness of mobile analysis

# Evidence It Should Collect

- Platform confirmation from multiple config files (HIGH confidence)
- Permission declarations from manifests/plists (HIGH confidence)
- Platform-specific code patterns (HIGH confidence)
- Behavior classification (product vs platform-specific) (MEDIUM confidence)

# Analysis Method

1. Detect platform from fingerprint
2. Delegate to: flutter-forensics OR android-forensics OR ios-forensics OR rn-forensics
3. Always activate mobile-ux-forensics alongside
4. Collect permissions from all platform sources
5. Classify each behavior by level (product, platform-specific, framework-specific)
6. Run completeness validation

# Expected Output

- `project_model.platform` — framework-specific configuration
- `project_model.permissions` — cross-platform permission inventory
- `project_model.mobile_journeys` — rich journey model with gestures
- `project_model.mobile_gestures` — per-screen gesture inventory

# Confidence Rules

- Platform detection: HIGH (deterministic from config)
- Permission extraction: HIGH (declarative in manifests)
- Behavior classification: MEDIUM (requires interpretation)
- Gesture detection: HIGH (observable from code)

# What This Skill Must Not Do

- Do not duplicate work of platform-specific forensics
- Do not assume runtime availability
- Do not evaluate business logic
- Do not modify analyzed project

# Related Skills

- flutter-forensics, android-forensics, ios-forensics, rn-forensics (delegates to)
- mobile-ux-forensics (activates alongside)
- project-archaeologist (reads fingerprint from)
