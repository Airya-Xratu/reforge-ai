---
name: ios-forensics
description: >
  Deep static analysis of native iOS (Swift/ObjC) projects. Reconstructs product
  from ViewControllers, SwiftUI views, NavigationStack, ObservableObject, CoreData,
  URLSession, and Xcode project configuration.
---

# Purpose

Extract iOS-specific product evidence from source code.

# When This Skill Activates

- mobile-analyzer detects iOS native project
- Fingerprint shows `framework: ios_native`

# Inputs

- `project_model.fingerprint`
- `ios/Runner/Info.plist`
- Xcode project configuration
- Source code (ViewControllers, SwiftUI views)
- Podfile / Package.swift

# Responsibilities

1. Extract permissions, URL schemes from Info.plist
2. Extract deployment target, dependencies from Podfile/SPM
3. Map ViewControllers and SwiftUI views to screens
4. Reconstruct state from ObservableObject/@Published
5. Reconstruct navigation from NavigationStack/NavigationView
6. Extract persistence from CoreData models
7. Extract networking from URLSession/Alamofire
8. Detect UIKit vs SwiftUI usage

# Expected Output

- Enriched project_model features, screens, states, design_system, architecture
- `project_model.platform.ios` — iOS-specific config

# What This Skill Must Not Do

- Do not require simulator or device
- Do not modify analyzed project

# Related Skills

- mobile-analyzer (orchestrates)
- mobile-ux-forensics (activates alongside)
