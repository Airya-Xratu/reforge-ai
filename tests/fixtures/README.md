# Test Fixtures

This directory contains test fixtures for validating Reforge's analysis capabilities.

## Planned Fixtures

### Flutter Projects
- `flutter-feature-first/` — Well-structured Flutter app
- `flutter-mixed-state/` — App with inconsistent state management
- `flutter-no-backend/` — App with no backend connectivity

### Android Projects
- `android-compose/` — Jetpack Compose app
- `android-xml/` — Traditional XML layout app

### iOS Projects
- `ios-swiftui/` — SwiftUI app
- `ios-uikit/` — UIKit app

### React Native Projects
- `rn-expo/` — Expo-managed app
- `rn-bare/` — Bare React Native app

### Edge Cases
- `contradictory-project/` — Documentation contradicts code
- `dead-features/` — Project with many unused features
- `minimal-project/` — Smallest possible project

## Usage

Each fixture is a minimal project structure (not a runnable app) containing enough files to test Reforge's analysis capabilities.
