# Mobile Analyzers

## Philosophy

Mobile applications often cannot be run by the AI agent. There is no emulator, no backend, no credentials.

Reforge performs **static product archaeology** — reconstructing the product purely from source code.

## Evidence Hierarchy

```
Runtime Evidence        ← never assume available
Visual Evidence         ← screenshots (optional)
Navigation Evidence     ← routes, screens
UI Implementation       ← widget trees, layouts
State Evidence          ← state management code
Data/API Evidence       ← models, API calls
Architecture Evidence   ← patterns, modules
Naming/String Evidence  ← class names, resources
```

## Platform Forensics

| Platform | Sub-Skill | Key Evidence Sources |
|---|---|---|
| Flutter | flutter-forensics | pubspec.yaml, lib/, widget trees, ThemeData |
| Android | android-forensics | Manifest, Gradle, Activities, ViewModels |
| iOS | ios-forensics | Info.plist, ViewControllers, SwiftUI |
| React Native | rn-forensics | package.json, components, hooks |

## Orchestrator

mobile-analyzer detects the platform and delegates to the correct forensics sub-skill. It always activates mobile-ux-forensics alongside.

## Cross-Stack Reconstruction

When rebuilding for a different platform:
1. Preserve product intent
2. Adapt platform conventions
3. Keep Product DNA
4. Update implementation patterns
