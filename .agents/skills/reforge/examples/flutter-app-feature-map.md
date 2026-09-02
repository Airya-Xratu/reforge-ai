# Feature Map: TaskMaster

## Feature Matrix

| Feature | Evidence | Confidence | User Value | Complexity | Status |
|---|---|---|---|---|---|
| Task Management | routes, screens, models, API | HIGH | high | medium | complete |
| Task Lists | screens, navigation, models | HIGH | high | low | complete |
| Task Detail | screen, components, actions | HIGH | high | low | complete |
| Task Creation | screen, form, validation, API | HIGH | high | medium | complete |
| Task Editing | screen, form, API | HIGH | medium | low | complete |
| Task Deletion | action, confirmation, API | HIGH | medium | low | complete |
| Task Completion | swipe action, state update | HIGH | high | low | complete |
| Search | route, screen, API, filters | HIGH | high | medium | complete |
| Filtering | filter chips, state, URL params | HIGH | medium | medium | complete |
| Sorting | sort options, state | MEDIUM | medium | low | complete |
| Contacts | screens, models, API | HIGH | medium | medium | complete |
| Contact Detail | screen, actions | HIGH | medium | low | complete |
| User Profile | screen, settings, API | HIGH | low | low | complete |
| Settings | screen, preferences, local storage | HIGH | low | low | complete |
| Dark Mode | theme, toggle, persistence | HIGH | low | low | complete |
| Push Notifications | Firebase config, handler | MEDIUM | medium | medium | partial |
| Calendar Integration | feature flag, partial screen | LOW | medium | high | partial |
| Offline Mode | local DB, sync service | MEDIUM | high | high | partial |
| Widget (Home Screen) | platform channel, widget config | LOW | low | high | stub |
| Share/Export | action, share dialog | MEDIUM | low | low | complete |

## Core Features (product fails without these)

1. **Task Management** — Create, edit, complete, delete tasks
2. **Task Lists** — Organize tasks into lists
3. **Search & Filter** — Find tasks quickly
4. **Contacts** — Associate tasks with people

## Secondary Features (differentiation, retention)

5. **Dark Mode** — User comfort
6. **Settings** — Personalization
7. **Push Notifications** — Engagement

## Nice-to-Have (experimental)

8. **Calendar Integration** — Partially built
9. **Offline Mode** — Partially built
10. **Home Screen Widget** — Stub only

## Feature Dependencies

```
Task Management
├── depends on: Auth
├── depends on: Network
├── enhances: Contacts (task ↔ contact link)
└── optional: Push Notifications

Search
├── depends on: Task Management
├── depends on: Contacts
└── standalone: false

Offline Mode
├── depends on: Local DB (Hive)
├── depends on: Sync Service
└── affects: Task Management, Contacts, Search
```

## Evidence Sources

| Feature | Primary Source | Secondary Sources |
|---|---|---|
| Task Management | `lib/features/tasks/` | `lib/data/models/task.dart`, API service |
| Search | `lib/features/search/` | Route config, search API |
| Contacts | `lib/features/contacts/` | `lib/data/models/contact.dart` |
