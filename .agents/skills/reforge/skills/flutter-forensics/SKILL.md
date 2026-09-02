---
name: flutter-forensics
description: >
  Deep static analysis of Flutter projects. Reconstructs product from widget trees,
  state management (BLoC/Provider/Riverpod/GetX/MobX), navigation (GoRouter/Navigator),
  themes, assets, and platform channels without runtime execution.
---

# Purpose

Extract Flutter-specific product evidence from source code.

# When This Skill Activates

- mobile-analyzer detects Flutter framework
- User asks to "analyze Flutter project"
- Fingerprint shows `framework: flutter`

# Inputs

- `project_model.fingerprint`
- `pubspec.yaml`
- `lib/` directory structure
- `android/` and `ios/` platform directories
- Generated files (*.g.dart, *.freezed.dart)

# Responsibilities

1. Analyze widget trees to reconstruct screen layouts
2. Detect state management approach and reconstruct state machines
3. Reconstruct navigation graph from routing configuration
4. Extract design system from ThemeData/AppTheme
5. Parse pubspec.yaml for dependencies, assets, fonts
6. Detect platform channels and native integrations
7. Analyze generated files for code generation patterns
8. Extract Android/iOS platform configuration

# Evidence It Should Collect

- Widget tree structure per screen (HIGH confidence)
- State classes and transitions (HIGH confidence)
- Route definitions and screen mappings (HIGH confidence)
- Theme tokens (colors, typography, spacing) (HIGH confidence)
- pubspec.yaml dependencies (HIGH confidence)
- Asset and font inventory (HIGH confidence)
- Platform channel definitions (HIGH confidence)
- Generated file inventory (HIGH confidence)

# Analysis Method

1. Parse pubspec.yaml for project metadata and dependencies
2. Scan `lib/` for widget files, state management, routing
3. Trace build() methods to reconstruct widget trees
4. Identify state classes (ChangeNotifier, Bloc, Cubit, etc.)
5. Map routes from GoRouter/Navigator/AutoRoute config
6. Extract ThemeData tokens
7. Scan platform directories for native config

# Expected Output

- Enriched `project_model.features` (new features from Flutter code)
- Enriched `project_model.screens` (widget tree details)
- Enriched `project_model.state_machines` (state transitions)
- Enriched `project_model.design_system` (theme tokens)
- Enriched `project_model.architecture` (state mgmt, navigation, DI)
- `project_model.platform.flutter` (Flutter-specific config)

# Confidence Rules

- pubspec.yaml parsing: HIGH (deterministic)
- Widget tree reconstruction: HIGH (traceable from source)
- State machine detection: HIGH (class hierarchy is observable)
- Route extraction: HIGH (config is declarative)
- Theme token extraction: HIGH (hardcoded values)
- Component purpose inference: MEDIUM (requires interpretation)

# What This Skill Must Not Do

- Do not execute Flutter code or require an emulator
- Do not analyze business logic meaning
- Do not evaluate UX quality
- Do not duplicate mobile-analyzer orchestration
- Do not modify analyzed project

# Related Skills

- mobile-analyzer (orchestrates this skill)
- mobile-ux-forensics (activates alongside)
- android-forensics, ios-forensics (platform config from this skill)
