---
name: android-forensics
description: >
  Deep static analysis of native Android (Kotlin/Java) projects. Reconstructs product
  from Activities, Fragments, Compose, ViewModels, Navigation, Hilt, Room, Retrofit,
  and Gradle configuration.
---

# Purpose

Extract Android-specific product evidence from source code.

# When This Skill Activates

- mobile-analyzer detects Android native project
- Fingerprint shows `framework: android_native`

# Inputs

- `project_model.fingerprint`
- `app/src/main/AndroidManifest.xml`
- `app/build.gradle` / `app/build.gradle.kts`
- Source code (Activities, Fragments, Compose, ViewModels)
- Resources (themes, colors, strings, navigation graphs)

# Responsibilities

1. Extract permissions, activities, services from Manifest
2. Extract SDK versions, dependencies from Gradle
3. Map Activities/Fragments/Compose screens
4. Reconstruct ViewModel state machines
5. Reconstruct navigation from Navigation Component
6. Extract networking from Retrofit interfaces
7. Extract persistence from Room entities/DAOs
8. Extract DI from Hilt modules
9. Extract design tokens from resources

# Expected Output

- Enriched project_model features, screens, states, design_system, architecture
- `project_model.platform.android` — Android-specific config

# What This Skill Must Not Do

- Do not require emulator or device
- Do not modify analyzed project

# Related Skills

- mobile-analyzer (orchestrates)
- mobile-ux-forensics (activates alongside)
