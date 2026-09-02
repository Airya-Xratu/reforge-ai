# Android Forensics

## What It Analyzes

- AndroidManifest.xml → permissions, activities, services, receivers
- Gradle → SDK versions, dependencies, flavors, signing
- Activities/Fragments/Compose → screens
- ViewModels → state management
- Navigation Component → navigation graph
- Room → persistence
- Retrofit → networking
- Hilt/Dagger → DI
- Resources → themes, colors, strings

## Detection Patterns

| Pattern | Indicates |
|---|---|
| `@Composable` | Jetpack Compose |
| `extends Fragment` | Fragment-based |
| `@HiltViewModel` | Hilt DI |
| `@Dao` / `@Entity` | Room database |
| `@GET` / `@POST` | Retrofit API |

## Key Files

- `app/src/main/AndroidManifest.xml`
- `app/build.gradle` or `app/build.gradle.kts`
- `app/src/main/java/` or `app/src/main/kotlin/`
- `app/src/main/res/`
