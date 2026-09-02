# Reforge Model

## How Reforge Works

Reforge transforms source code analysis into product understanding.

```
Repository
    ↓
Evidence
    ↓
Project Model
    ↓
Specialist Skills
    ↓
Reconstructed Intent
    ↓
Product DNA
    ↓
Decision / Plan
```

## Components

### Evidence

Observable facts from source code. Every finding traces to evidence.

### Project Model

Shared intermediate representation. All skills read/write this. See [Project Model](project-model.md).

### Specialist Skills

Narrow, focused analysis capabilities. Each has a defined scope, inputs, outputs, and confidence rules.

### Orchestrator

Root skill that routes user intent to the right specialist skills. Does not do analysis itself.

### Decision Model

Records reasoning, alternatives, and tradeoffs for every non-obvious recommendation.

## Lenses

Every analysis can view the project through four lenses:

| Lens | Focus |
|---|---|
| Product | Purpose, users, features, business goals |
| UX | Journeys, interactions, accessibility, edge cases |
| UI | Visual design, components, design system |
| Engineering | Architecture, dependencies, testing, tech debt |

Lenses are analytical perspectives, not the skill architecture.
