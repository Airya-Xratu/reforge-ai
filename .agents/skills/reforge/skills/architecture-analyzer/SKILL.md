---
name: architecture-analyzer
description: >
  Software architect lens. Reconstructs architecture patterns, module boundaries,
  dependency graphs, state management, networking, persistence, DI, testing, and
  identifies technical debt.
---

# Purpose

Understand how the software is built and where the risks are.

# When This Skill Activates

- User asks about architecture, modules, dependencies, tech debt
- Part of UNDERSTAND, REDESIGN, REBUILD workflows
- After fingerprint is established

# Inputs

- `project_model.fingerprint`
- Source code directory structure
- Configuration files (build configs, DI setup)
- Test directories

# Responsibilities

1. Detect architecture pattern (feature-first, clean, MVVM, etc.)
2. Map module boundaries and dependencies
3. Detect circular dependencies, god modules, orphan modules
4. Reconstruct state management architecture
5. Analyze networking layer
6. Analyze persistence layer
7. Analyze DI configuration
8. Assess test architecture
9. Detect CI/CD setup
10. Identify technical debt and architectural risks

# Evidence It Should Collect

- Module boundaries from directory structure (HIGH confidence)
- Dependency direction from imports (HIGH confidence)
- Circular dependencies from import analysis (HIGH confidence)
- State management from class hierarchies (HIGH confidence)
- Networking from API client code (HIGH confidence)
- Persistence from database/storage code (HIGH confidence)
- DI from registration code (HIGH confidence)
- Test coverage from test file counts (MEDIUM confidence)
- Tech debt from TODO/FIXME counts (MEDIUM confidence)

# Analysis Method

1. Map directory structure to module boundaries
2. Trace imports to build dependency graph
3. Detect patterns from class hierarchies and frameworks
4. Analyze networking, persistence, DI layers
5. Count and categorize tests
6. Scan for technical debt signals

# Expected Output

- `project_model.architecture` — pattern, modules, deps, networking, persistence, DI, testing, CI/CD
- `project_model.data_models` — domain models
- `project_model.api_contracts` — API endpoints

# Confidence Rules

- Architecture pattern: HIGH (observable from structure)
- Module boundaries: HIGH (from directory layout)
- Circular dependencies: HIGH (from import analysis)
- Technical debt: MEDIUM (requires interpretation)
- Test coverage: MEDIUM (file count ≠ coverage)

# What This Skill Must Not Do

- Do not evaluate product quality
- Do not assess visual design
- Do not modify analyzed project

# Related Skills

- project-archaeologist (provides fingerprint)
- feature-mapper (provides feature boundaries)
- state-analyzer (provides state management details)
