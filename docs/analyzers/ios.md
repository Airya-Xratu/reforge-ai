# iOS Forensics

## What It Analyzes

- Info.plist → permissions, URL schemes, capabilities
- Xcode project → targets, build settings
- ViewControllers (UIKit) → screens
- SwiftUI Views → screens
- ObservableObject/@Published → state management
- NavigationStack/NavigationView → navigation
- CoreData → persistence
- URLSession/Alamofire → networking

## Detection Patterns

| Pattern | Indicates |
|---|---|
| `import SwiftUI` | SwiftUI |
| `import UIKit` | UIKit |
| `@StateObject` | SwiftUI state |
| `ObservableObject` | State management |
| `NavigationStack` | Modern navigation |

## Key Files

- `ios/Runner/Info.plist`
- `ios/Podfile`
- `ios/Runner.xcodeproj/`
- Source files in `ios/Runner/`
