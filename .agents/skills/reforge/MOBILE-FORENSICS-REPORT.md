# Reforge Mobile Forensics — Architecture Report

## What Was Added

### New Sub-Skills (5)

| Sub-Skill | Purpose | Key Capabilities |
|---|---|---|
| `flutter-forensics` | Flutter static analysis | Widget trees, BLoC/Provider/Riverpod/GetX/MobX state, GoRouter/Navigator routes, ThemeData, pubspec.yaml, platform channels, generated files |
| `android-forensics` | Android native static analysis | AndroidManifest, Gradle, Activities/Fragments/Compose, ViewModels, Navigation Component, Hilt/Dagger, Room, Retrofit, resources |
| `ios-forensics` | iOS native static analysis | Info.plist, Xcode project, UIKit/SwiftUI, ViewControllers, NavigationStack, ObservableObject, CoreData, URLSession/Alamofire |
| `rn-forensics` | React Native/Expo static analysis | package.json, Expo config, components, React Navigation/Expo Router, Redux/Zustand/Context, React Query, native modules |
| `mobile-ux-forensics` | Mobile UX reconstruction | Gestures, keyboard behavior, safe areas, orientation, status bar, modals, haptics, permissions, biometrics, app lifecycle, deep links, notifications, share sheets |

### New Script (1)

| Script | Purpose |
|---|---|
| `mobile-stack-detector` | Detects mobile framework, extracts permissions, platform config, key dependencies, navigation type |

### New Project Model Sections (3)

| Section | Purpose |
|---|---|
| `platform` | Framework-specific config (Flutter/Android/iOS/RN), behavior classification |
| `mobile_journeys` | Rich journey model: steps, gestures, decisions, interruptions, errors, recovery, abandonment |
| `mobile_gestures` | Per-screen gesture inventory with actions and feedback |

### Updated Files

| File | Change |
|---|---|
| `mobile-analyzer/SKILL.md` | Rewritten as orchestrator with delegation map |
| `parent SKILL.md` | Added `MOBILE_FORENSICS` output mode, 5 new sub-skill entries |
| `project-model.yaml` | Added 3 new sections (platform, mobile_journeys, mobile_gestures) |

## Mobile Evidence Model

```
Runtime Evidence        ← never assume available
Visual Evidence         ← screenshots, recordings (optional)
Navigation Evidence     ← routes, screens, navigation config
UI Implementation       ← widget trees, layouts, components
State Evidence          ← state management, ViewModels, stores
Data/API Evidence       ← models, API calls, persistence
Architecture Evidence   ← patterns, modules, DI
Naming/String Evidence  ← class names, resource strings, comments
```

## Orchestration Flow

```
User: "Analyze this Flutter project"
    ↓
mobile-analyzer (orchestrator)
    ├── Detect: Flutter
    ├── Load: flutter-forensics
    ├── Load: mobile-ux-forensics
    ├── Flutter forensics → project_model.features, screens, states, design_system
    ├── Mobile UX forensics → project_model.ux, mobile_journeys, mobile_gestures
    └── Orchestrator → project_model.platform, permissions, validation
```

## File Count

| Category | Before | After |
|---|---|---|
| Sub-skills | 22 | 27 |
| Scripts | 6 | 7 |
| Templates | 11 | 11 |
| Examples | 5 | 5 |
| Reports | 1 | 2 |
| **Total** | **45** | **52** |

## What Each Forensics Sub-Skill Extracts

### Flutter
- Widget trees → screen layout, component hierarchy
- StatefulWidget/StatelessWidget → stateful vs stateless screens
- Provider/BLoC/Riverpod/GetX/MobX → state management
- GoRouter/Navigator/AutoRoute → navigation graph
- ThemeData/AppTheme → design system
- pubspec.yaml → dependencies, assets, fonts
- Platform channels → native integrations
- Generated files → code generation patterns

### Android
- AndroidManifest → permissions, activities, services, receivers, deep links
- Gradle → SDK versions, dependencies, flavors, signing
- Activities/Fragments/Compose → screens
- ViewModels → state management
- Navigation Component → navigation graph
- Room → persistence
- Retrofit → networking
- Hilt/Dagger → DI
- Resources → themes, colors, strings, drawables

### iOS
- Info.plist → permissions, URL schemes, capabilities
- Xcode project → targets, build settings
- UIKit ViewControllers → screens
- SwiftUI Views → screens
- ObservableObject/@Published → state management
- NavigationStack/NavigationView → navigation
- CoreData → persistence
- URLSession/Alamofire → networking

### React Native / Expo
- package.json → dependencies, scripts
- app.json → Expo config, plugins
- Components → screens
- React Navigation/Expo Router → navigation
- Redux/Zustand/Context → state management
- React Query → data fetching
- Platform.* files → platform-specific behavior
- Native modules → native capabilities

## Cross-Stack Behavior Classification

| Behavior | Level | Example |
|---|---|---|
| Task creation flow | product | Same intent across all platforms |
| Pull-to-refresh | product | Standard mobile pattern |
| iOS swipe-back | ios_specific | iOS convention |
| Android back button | android_specific | Android convention |
| Cupertino transitions | framework_specific | Flutter Cupertino widget |
| Material bottom sheets | product | Cross-platform UI |

## Output

All mobile forensics findings write to the shared `project_model`. No isolated files.
