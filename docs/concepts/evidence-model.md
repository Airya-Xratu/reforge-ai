# Evidence Model

## The Principle

Every Reforge finding must be classified by its evidence level.

The system must never present an inference as an observed fact.

## Levels

### OBSERVED

Directly visible in source code.

```yaml
finding:
  statement: "The application uses Provider for state management."
  classification: OBSERVED
  confidence: HIGH
  evidence:
    - source: "pubspec.yaml"
      detail: "provider: ^6.0.0 in dependencies"
    - source: "lib/providers/"
      detail: "Directory with 8 ChangeNotifier classes"
```

### INFERRED

Conclusion drawn from multiple observations.

```yaml
finding:
  statement: "The bottom navigation represents the three primary user journeys."
  classification: INFERRED
  confidence: MEDIUM
  evidence:
    - source: "lib/main.dart"
      detail: "BottomNavigationBar with 3 items"
    - source: "lib/features/"
      detail: "3 feature directories match tab structure"
```

### HYPOTHESIZED

Plausible but not confirmed.

```yaml
finding:
  statement: "The app likely caches task data for offline use."
  classification: HYPOTHESIZED
  confidence: LOW
  evidence:
    - source: "lib/services/cache_service.dart"
      detail: "Cache service exists but unclear if task data uses it"
```

### RECOMMENDED

Suggestion, not fact.

```yaml
finding:
  statement: "Consider adding error states to the profile screen."
  classification: RECOMMENDED
  confidence: MEDIUM
  evidence:
    - source: "lib/features/profile/"
      detail: "No error state handling found in ProfileBloc"
```

## Rules

1. OBSERVED findings require direct source code evidence
2. INFERRED findings require multiple supporting observations
3. HYPOTHESIZED findings require at least one partial observation
4. RECOMMENDED findings identify gaps or improvements
5. Never present INFERRED as OBSERVED
6. Never present HYPOTHESIZED as INFERRED
