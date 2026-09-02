# Reforge

> **Reverse-engineer the product. Understand the system. Forge the next version.**

Reforge is an open-source Agent Skill system that helps AI coding agents understand existing software projects — especially mobile applications — and reconstruct the product they represent.

It doesn't clone code. **Reforge reconstructs intent.**

---

## The Problem

When an AI coding agent encounters a mobile application repository, it sees files, classes, and dependencies. It doesn't see the product.

Mobile makes this worse. The agent may have:

- No emulator, simulator, or device
- No backend or API credentials
- No signing configuration
- No native SDKs

Reforge solves this by performing **static product archaeology** — reconstructing features, screens, states, UX patterns, design systems, and architecture purely from source code.

## How It Works

```
Existing Project
      ↓
Project Fingerprint
      ↓
Repository Archaeology
      ↓
Architecture Reconstruction
      ↓
Feature Discovery
      ↓
Screen & State Analysis
      ↓
UX Reconstruction
      ↓
UI Reconstruction
      ↓
Design System Extraction
      ↓
Product Reconstruction
      ↓
Product DNA
      ↓
Rebuild / Redesign / Adapt
```

## Core Concepts

| Concept | Description |
|---|---|
| **Project Model** | Shared intermediate representation between all skills |
| **Product DNA** | Characteristics that define the product beyond its source code |
| **Evidence Model** | Every finding classified as OBSERVED, INFERRED, HYPOTHESIZED, or RECOMMENDED |
| **MAS** | Minimum Architectural Skeleton — smallest runnable project preserving architecture |
| **MVC** | Minimum Viable Clone — smallest useful reconstruction of product experience |

## Workflows

| Workflow | Description |
|---|---|
| **UNDERSTAND** | Analyze existing project, produce complete reconstruction |
| **REDESIGN** | Understand → identify problems → propose improvements |
| **REFERENCE** | Extract reusable patterns from a reference application |
| **REBUILD** | Reconstruct product → produce implementation strategy |
| **BOILERPLATE** | Extract architecture → generate Minimum Architectural Skeleton |

## Supported Ecosystems

| Ecosystem | Status |
|---|---|
| Flutter | Supported |
| Android (Kotlin/Java) | Supported |
| iOS (Swift/ObjC) | Supported |
| React Native / Expo | Supported |
| Web (Next.js, Vue) | Planned |

## Agent Compatibility

Reforge works as an Agent Skill compatible with:

- Claude Code
- Codex
- Gemini CLI
- Freebuff
- Other Agent Skills-compatible agents

## Project Structure

```
.agents/skills/reforge/
├── SKILL.md                    # Orchestrator
├── skills/                     # 27 specialist skills
├── schemas/                    # Project Model schema
├── templates/                  # Output templates
├── examples/                   # Example project models
└── scripts/                    # Deterministic analysis tools

docs/                           # Architecture documentation
.github/                        # GitHub community & CI
tests/                          # Validation fixtures
```

## Quick Start

1. Clone this repository
2. Open it in your AI coding agent
3. Ask the agent to analyze a mobile project using Reforge
4. The agent loads the orchestrator skill, which delegates to specialists

## Roadmap

See [ROADMAP.md](ROADMAP.md) for the full plan.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to add skills, analyzers, and documentation.

## License

MIT — see [LICENSE](LICENSE).
