# Screen Specification: TaskListScreen

## Overview

| Field | Value |
|---|---|
| Screen ID | screen_001 |
| Screen Name | TaskListScreen |
| Purpose | Display and manage a list of tasks with filtering and sorting |
| Type | full_page |
| File | `lib/features/tasks/presentation/screens/task_list_screen.dart` |

## Entry Points

| From | Trigger | Route |
|---|---|---|
| HomeScreen | Tap "Tasks" tab | /tasks |
| SearchScreen | Tap task result | /tasks/:id (opens detail, not list) |
| Deep link | myapp://tasks | /tasks |
| Notification | Tap task notification | /tasks/:id |

## Exit Points

| To | Trigger | Type |
|---|---|---|
| TaskDetailScreen | Tap task card | navigation push |
| TaskCreateScreen | Tap FAB | navigation push |
| FilterBottomSheet | Tap filter icon | bottom sheet |
| SortBottomSheet | Tap sort icon | bottom sheet |

## Layout

```
┌─────────────────────────────┐
│ AppBar                      │
│ [Tasks]    [Search] [Filter]│
├─────────────────────────────┤
│ Filter Chips (when active)  │
│ [Priority: High] [x]        │
├─────────────────────────────┤
│                             │
│ TaskCard                    │
│ ┌─────────────────────────┐ │
│ │ ● High    2024-01-15    │ │
│ │ Task title here         │ │
│ │ Contact: John Doe       │ │
│ │ ▪▪▪▪▪□□□□ 40%          │ │
│ └─────────────────────────┘ │
│                             │
│ TaskCard                    │
│ ┌─────────────────────────┐ │
│ │ ○ Low     2024-01-20    │ │
│ │ Another task            │ │
│ └─────────────────────────┘ │
│                             │
├─────────────────────────────┤
│ [FAB: +]                    │
└─────────────────────────────┘
```

## Components

| Component | Type | Purpose | States |
|---|---|---|---|
| TaskAppBar | Custom AppBar | Title + search/filter actions | default |
| FilterChipBar | Horizontal scroll | Active filters display | empty, active |
| TaskCard | Custom card | Task preview | default, completed, overdue |
| EmptyState | Widget | No tasks message | hidden, visible |
| LoadingIndicator | CircularProgressIndicator | Loading | hidden, visible |
| FloatingActionButton | Material FAB | Create task | default, pressed |

## Data

| Field | Source | Required | Cached |
|---|---|---|---|
| tasks | TaskBloc state | yes | yes (Hive) |
| filters | FilterBloc state | no | yes (local) |
| sort_preference | SettingsService | no | yes (SharedPreferences) |

## Actions

| Action | Trigger | Requires | Confirmation | Result |
|---|---|---|---|---|
| Create task | FAB tap | auth | no | push to CreateScreen |
| View task | Card tap | none | no | push to DetailScreen |
| Complete task | Swipe right | none | no | state update + snackbar |
| Delete task | Swipe left | none | undo snackbar | state update + API call |
| Filter | Filter icon tap | none | no | show bottom sheet |
| Sort | Sort icon tap | none | no | show bottom sheet |
| Search | Search icon tap | none | no | push to SearchScreen |

## States

| State | Description | UI Shown | Trigger |
|---|---|---|---|
| initial | Screen just mounted | LoadingIndicator | initState |
| loading | Fetching tasks | LoadingIndicator | API call |
| loaded | Tasks ready | TaskCard list | data received |
| empty | No tasks match | EmptyState with CTA | empty result |
| error | Request failed | ErrorWidget + retry | API error |
| refreshing | Pull-to-refresh | TaskCard list + RefreshIndicator | pull gesture |
| offline | No network | Cached list + OfflineBanner | connectivity change |
| search_active | Search field open | Filtered list | search icon tap |

## Platform-Specific Behavior

| Platform | Behavior |
|---|---|
| Android | Back button dismisses search, standard material transitions |
| iOS | Swipe-back gesture, cupertino page transition optional |

## Permissions

| Permission | Required For | When |
|---|---|---|
| none | — | — |

## Evidence

| Finding | Source | Confidence |
|---|---|---|
| Screen exists | `task_list_screen.dart` line 1 | HIGH |
| Uses BLoC | `BlocBuilder<TaskBloc, TaskState>` line 45 | HIGH |
| Swipe actions | `Dismissible` widget line 78 | HIGH |
| Empty state | `EmptyStateWidget` line 112 | HIGH |
| FAB navigation | `onPressed: () => context.push('/tasks/create')` line 95 | HIGH |
