# Product DNA: TaskMaster

> What should survive a redesign even if implementation changes.

## Interaction DNA

```yaml
interaction:
  - task_oriented          # Every screen serves a task completion goal
  - fast_completion        # Core actions reachable in ≤3 taps
  - keyboard_first         # Search and filter always accessible
  - swipe_actions          # Swipe to complete/delete is primary interaction
  - minimal_modals         # Bottom sheets preferred over dialogs
```

**Evidence:** Swipe actions in list screens, FAB for primary action, search always in AppBar.
**Confidence:** HIGH

## Visual DNA

```yaml
visual:
  - professional           # Clean, business-oriented aesthetic
  - data_dense             # Information-rich screens, not minimal
  - color_coded_status     # Priority and status use distinct colors
  - card_based             # Items displayed as cards with clear hierarchy
  - minimal_illustrations  # No decorative art, functional only
```

**Evidence:** Card layouts throughout, color constants for priority levels, no onboarding illustrations.
**Confidence:** HIGH

## UX DNA

```yaml
ux:
  - progressive_disclosure  # Details hidden until needed
  - low_friction            # Minimal steps to complete tasks
  - offline_capable         # Cached data available offline
  - undo_over_confirm       # Undo snackbar instead of confirmation dialogs
  - batch_operations        # Multi-select for bulk actions
```

**Evidence:** Undo snackbar after delete, offline indicator with cached data, multi-select mode.
**Confidence:** MEDIUM (offline capability partially implemented)

## Product DNA

```yaml
product:
  - utility                 # Tool, not entertainment
  - productivity            # Helps users accomplish work
  - personal_management     # Individual task organization
  - lightweight_crm         # Contact and deal tracking
```

**Evidence:** Task model with contacts, deal pipeline, calendar integration.
**Confidence:** HIGH

## What Must Survive Redesign

1. **Speed** — Core task flow is fast. Don't add steps.
2. **Swipe interactions** — Users expect swipe-to-act.
3. **Color-coded status** — Visual scanning depends on it.
4. **Offline support** — Users work in poor connectivity.
5. **Undo pattern** — Reduces anxiety about destructive actions.
6. **Data density** — Users want overview, not whitespace.
