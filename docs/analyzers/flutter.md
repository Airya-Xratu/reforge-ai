# Flutter Forensics

## What It Analyzes

- Widget trees → screen layouts
- StatefulWidget/StatelessWidget → stateful vs stateless
- BLoC/Provider/Riverpod/GetX/MobX → state management
- GoRouter/Navigator/AutoRoute → navigation
- ThemeData/AppTheme → design system
- pubspec.yaml → dependencies, assets, fonts
- Platform channels → native integrations
- Generated files → code generation patterns

## State Management Detection

| Import Pattern | Approach |
|---|---|
| `provider` | Provider/ChangeNotifier |
| `flutter_bloc` | BLoC/Cubit |
| `flutter_riverpod` | Riverpod |
| `get` | GetX |
| `mobx` | MobX |

## Navigation Detection

| Package | Pattern |
|---|---|
| `go_router` | Declarative routing |
| `auto_route` | Code-generated routing |
| Navigator 1.0 | Imperative push/pop |
| GetX | Get.to / Get.toNamed |

## Key Files

- `pubspec.yaml` — project metadata
- `lib/` — Dart source
- `android/` — Android platform config
- `ios/` — iOS platform config
