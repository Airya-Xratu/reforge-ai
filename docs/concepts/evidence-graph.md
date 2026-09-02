# Evidence Graph

## What It Is

The Evidence Graph maps relationships between findings in the Project Model.

```
Feature
 ├── contains → Screen
 ├── uses → Component
 ├── reads → State
 ├── calls → API
 ├── requires → Permission
 └── belongs to → User Journey

Screen
 ├── navigates → Screen
 ├── renders → Component
 ├── consumes → State
 ├── triggers → Action
 └── belongs to → Feature
```

## Purpose

The graph enables impact analysis. When you change one element, you can trace what else is affected.

## Usage

### Impact Analysis

```
Change: Modify TaskCard component
Direct impact: TaskListScreen, SearchResultsScreen, ProfileScreen
Cascading: All features using those screens
Test impact: All widget tests rendering TaskCard
```

### Completeness Check

```
Feature without screens → possibly dead
Screen without entry point → unreachable
State without consumers → unused
API without UI trigger → backend-only
```

### Contradiction Detection

```
Route without screen → broken navigation
Screen without state → missing state management
Component without usage → dead code
```

## Implementation

The graph is implicit in the Project Model's cross-references. Skills build it by reading IDs and relationships across sections.
