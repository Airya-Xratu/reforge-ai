# Project Model

## What It Is

The Project Model is the shared intermediate representation between all Reforge skills.

When the architecture-analyzer discovers module boundaries, it writes to the Project Model. When the feature-mapper needs to know the architecture pattern, it reads from the Project Model.

This enables composition: skills don't need to know about each other, only about the Project Model.

## Structure

The Project Model has 23 sections:

1. **Fingerprint** — project identification
2. **Features** — feature inventory
3. **Screens** — screen inventory
4. **State Machines** — state transitions
5. **Navigation** — navigation graph
6. **UX** — user experience patterns
7. **Design System** — visual tokens
8. **Architecture** — technical structure
9. **Data Models** — domain entities
10. **API Contracts** — endpoints
11. **Permissions** — required permissions
12. **Dependencies** — package inventory
13. **Contradictions** — claims vs reality
14. **Dead Code** — unused artifacts
15. **Product** — purpose, users, goals
16. **Product DNA** — defining characteristics
17. **Git Evidence** — history-based findings
18. **Project Health** — quality scores
19. **Mobile Platform** — platform-specific config
20. **Mobile Journeys** — rich journey model
21. **Mobile Gestures** — gesture inventory
22. **Decision Log** — reasoning records
23. **Human Overrides** — user preferences

## Schema

See `schemas/project-model.schema.yaml` for the complete schema.

## Rules

- Every skill reads relevant sections and writes its findings
- No skill writes to sections outside its responsibility
- Evidence is mandatory for every finding
- Confidence levels are mandatory
- The model is append-only during analysis (no deletions)
