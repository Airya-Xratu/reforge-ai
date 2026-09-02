---
name: project-archaeologist
description: >
  Entry point for all Reforge analysis. Creates project fingerprint, performs repository
  archaeology, detects contradictions, and identifies dead code.
  Loads first in every pipeline.
---

# Purpose

Build the initial understanding of a project: what it is, how it's structured, and where the evidence lives.

# When This Skill Activates

- Always, as the first step in any Reforge workflow
- When user asks "what is this project?"
- When other skills need fingerprint data

# Inputs

- Project root directory
- Source code files
- Configuration files (pubspec.yaml, build.gradle, package.json, etc.)
- Documentation files
- Git history (optional)

# Responsibilities

1. Detect framework, language, project structure pattern
2. Detect state management, DI, navigation, backend type
3. Detect test coverage and platforms
4. Scan directory structure for feature boundaries
5. Detect conventions (naming, structure, patterns)
6. Compare documentation claims vs code reality
7. Identify probable dead code (screens, components, services, deps)
8. Extract git history evidence (optional)

# Evidence It Should Collect

- Framework detection from config files (HIGH confidence)
- Language detection from file extensions (HIGH confidence)
- Structure pattern from directory layout (HIGH confidence)
- State management from imports and class hierarchies (HIGH confidence)
- DI framework from config and registration code (HIGH confidence)
- Contradictions between docs and code (MEDIUM confidence)
- Dead code candidates from unused exports/imports (MEDIUM confidence)
- Git churn from commit history (MEDIUM confidence)

# Analysis Method

1. Run `scripts/project-fingerprint` for deterministic detection
2. Manually verify and refine automated findings
3. Scan documentation for claims
4. Cross-reference claims with code evidence
5. Identify unused artifacts
6. Optionally run `scripts/git-analyzer` for history evidence

# Expected Output

- `project_model.fingerprint` — complete project identification
- `project_model.contradictions` — claims vs reality mismatches
- `project_model.dead_code` — probable unused artifacts
- `project_model.git_evidence` — history-based findings (optional)

# Confidence Rules

- Framework/language detection: HIGH (deterministic)
- Structure pattern: HIGH (observable from directory layout)
- State management: HIGH (observable from imports and classes)
- Contradictions: MEDIUM (requires interpretation)
- Dead code: MEDIUM (may have indirect usage)
- Git churn: LOW-MEDIUM (history is evidence, not proof)

# What This Skill Must Not Do

- Do not analyze business logic or product meaning
- Do not evaluate UX quality
- Do not recommend architectural changes
- Do not modify any files in the analyzed project
- Do not make runtime assumptions

# Related Skills

- architecture-analyzer (depends on fingerprint data)
- mobile-analyzer (extends fingerprint for mobile)
- feature-mapper (uses fingerprint for context)
