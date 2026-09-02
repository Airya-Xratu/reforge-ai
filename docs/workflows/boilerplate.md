# Boilerplate Workflow

## Purpose

Extract architecture from existing project and generate a runnable skeleton.

## Trigger

- "Create minimal skeleton"
- "Generate MAS"
- "Scaffold this architecture"

## Skills Involved

1. project-archaeologist (fingerprint)
2. architecture-analyzer (architecture patterns)
3. design-system-extractor (design tokens)
4. boilerplate-generator (MAS generation)

## Output

- Generated project in `reforge/reconstruction/mas/`
- Preserves: framework, structure, state management, navigation, design system
- Removes: business logic, secrets, production data

## MAS vs MVC

| | MAS | MVC |
|---|---|---|
| Focus | Architecture | Product experience |
| Preserves | Structure, patterns | Screens, journeys, UI |
| Removes | Business logic | All non-essential features |
| Use case | Starting a new project | Demonstrating product value |
