---
name: reforge
description: >
  Open-source Agent Skill for reverse-engineering software intent.
  Reconstructs product, UX, UI, and architecture from static code analysis.
  Mobile-first. Evidence-driven. Progressive disclosure.
  Trigger: "reforge", "reverse engineer", "analyze this app", "reconstruct product",
  "product archaeology", "understand this project", "redesign this project".
version: 1.0.0
---

# Reforge

> Reverse-engineer the product. Understand the system. Forge the version.

## What Reforge Does

Reforge helps AI coding agents understand existing software projects and reconstruct the product they represent. It does not clone code. It reconstructs intent.

## Principles

1. **Evidence before inference.** Every conclusion traces to source code.
2. **OBSERVED > INFERRED > HYPOTHESIZED > RECOMMENDED.** Never present inference as fact.
3. **Static archaeology first.** Mobile projects often cannot run. Source code is truth.
4. **Progressive disclosure.** Load only what the user needs.
5. **Do NOT modify analyzed project** unless explicitly instructed.

## How This Skill Works

Reforge is not one giant prompt. It is an orchestration layer that:

1. Understands the user's goal
2. Inspects the project
3. Builds a **Project Model** (shared intermediate representation)
4. Determines which specialist skills are relevant
5. Activates only those skills
6. Combines findings
7. Detects contradictions
8. Produces actionable output

## Four Lenses

Every analysis can view the project through four lenses:

| Lens | Questions Answered |
|---|---|
| **Product** | What does it do? For whom? Why? |
| **UX** | How do users interact? What journeys exist? |
| **UI** | What does it look like? What design system? |
| **Engineering** | How is it built? What architecture? |

These are analytical perspectives, not the sub-skill architecture.

## Workflows

Route to the correct workflow based on user intent.

### UNDERSTAND

> "Analyze this project" / "What is this app?"

Activate: project-archaeologist → feature-mapper → screen-analyzer → state-analyzer → architecture-analyzer → ux-analyst → ui-analyst → design-system-extractor → product-analyst → project-health → documentation-generator

### REDESIGN

> "Redesign this project" / "How should we rebuild this?"

Activate: project-archaeologist → redesign-planner → reference-analyzer → impact-analyzer → implementation-planner

### REFERENCE

> "Use this as inspiration" / "Analyze as reference"

Activate: project-archaeologist → reference-analyzer

### REBUILD

> "Rebuild this" / "Create implementation plan"

Activate: project-archaeologist → architecture-analyzer → design-system-extractor → implementation-planner → test-planner

### BOILERPLATE

> "Create minimal skeleton" / "Generate MAS"

Activate: project-archaeologist → architecture-analyzer → design-system-extractor → boilerplate-generator

### ADD FEATURE

> "Add a feature" / "Plan new feature"

Activate: project-archaeologist → feature-mapper → screen-analyzer → state-analyzer → feature-planner → impact-analyzer → implementation-planner → test-planner

### MOBILE FORENSICS

> "Analyze Flutter/Android/iOS/RN project"

Activate: mobile-analyzer (orchestrator) → platform-specific forensics + mobile-ux-forensics

### HEALTH

> "Project health" / "Technical debt"

Activate: project-archaeologist → architecture-analyzer → project-health

### HANDOFF

> "Document for another agent"

Activate: documentation-generator (requires prior analysis)

## Incremental Analysis

When user asks about one feature, screen, or flow:
1. Load project-archaeologist for fingerprint only
2. Load relevant domain skill
3. Write to project model sections relevant to scope
4. Skip contradiction detection, health scoring, full pipeline

## Sub-Skills

All sub-skills live in `skills/`. Each has a `SKILL.md` with: purpose, activation triggers, inputs, responsibilities, evidence, output, confidence rules.

| Skill | Purpose |
|---|---|
| project-archaeologist | Fingerprint, archaeology, contradictions, dead code |
| mobile-analyzer | Orchestrator for platform-specific forensics |
| flutter-forensics | Flutter static analysis |
| android-forensics | Android native static analysis |
| ios-forensics | iOS native static analysis |
| rn-forensics | React Native/Expo static analysis |
| mobile-ux-forensics | Mobile UX patterns, gestures, lifecycle |
| product-analyst | Product purpose, personas, DNA |
| ux-analyst | Information architecture, journeys, interactions |
| ui-analyst | Visual hierarchy, components, layout |
| visual-forensics | Screenshot/recording analysis |
| design-system-extractor | Colors, typography, spacing, tokens |
| architecture-analyzer | Patterns, modules, deps, tech debt |
| feature-mapper | Feature discovery, navigation reconstruction |
| screen-analyzer | Screen inventory, entry/exit, composition |
| state-analyzer | State machines, edge cases, shared state |
| reference-analyzer | Preserve/redesign/remove decisions |
| redesign-planner | Current→problems→principles→proposed |
| feature-planner | Feature spec, stories, data model, API |
| boilerplate-generator | MAS generation |
| minimum-viable-clone | MVC generation |
| impact-analyzer | Blast radius estimation |
| implementation-planner | Phased plan, file plan |
| test-planner | Test strategy, cases, acceptance criteria |
| documentation-generator | Agent handoff document |
| project-health | Health scoring with evidence |
| decision-logger | Decision recording with reasoning |

## Project Model

All skills read/write `schemas/project-model.schema.yaml`. This is the shared contract. Findings never go to isolated files only.

## Output

Analysis writes to `reforge/`:
```
reforge/
├── project-model.yaml
├── product/
├── ux/
├── ui/
├── engineering/
├── reconstruction/
└── agent-handoff.md
```
