# React Native / Expo Forensics

## What It Analyzes

- package.json → dependencies, scripts
- app.json / app.config.js → Expo config
- Components → screens
- React Navigation / Expo Router → navigation
- Redux/Zustand/Context → state management
- React Query → data fetching
- Hooks → shared logic
- Platform-specific files → .ios.tsx, .android.tsx

## Detection Patterns

| Pattern | Indicates |
|---|---|
| `app/_layout.tsx` | Expo Router |
| `createStackNavigator` | React Navigation |
| `createSlice` | Redux Toolkit |
| `create(` | Zustand |
| `useQuery` | React Query |

## Key Files

- `package.json`
- `app.json` or `app.config.js` (Expo)
- `src/` or root component directory
- `android/`, `ios/` (native projects)
