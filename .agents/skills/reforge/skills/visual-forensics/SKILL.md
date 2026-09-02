---
name: visual-forensics
description: >
  Analyzes screenshots, recordings, design files. Compares visual evidence against
  source-code evidence and reports contradictions.
---

# Purpose

Bridge the gap between visual artifacts and source code.

# When This Skill Activates

- Screenshots, recordings, or design files are provided
- User asks to compare visual output to code
- User provides mockups alongside implementation

# Inputs

- Screenshots, recordings, design files (provided by user)
- `project_model.design_system`
- `project_model.screens`

# Responsibilities

1. Analyze visual artifacts for layout, typography, colors, spacing
2. Identify components in visual artifacts
3. Compare visual evidence against code evidence
4. Detect contradictions between visual and code
5. Extract visual patterns not visible in code

# Evidence It Should Collect

- Layout structure from screenshots (MEDIUM confidence)
- Color values from screenshots (MEDIUM confidence)
- Typography from screenshots (LOW-MEDIUM confidence)
- Component identification (MEDIUM confidence)
- Contradictions with code (HIGH confidence when found)

# Analysis Method

1. Analyze each visual artifact
2. Extract observable design properties
3. Cross-reference with project_model.design_system
4. Report matches and mismatches
5. Add contradictions to project_model

# Expected Output

- Enriched `project_model.design_system` (visual findings)
- `project_model.contradictions` (if mismatches found)

# Confidence Rules

- Visual extraction: MEDIUM (depends on image quality)
- Contradiction detection: HIGH (when visual disagrees with code)
- Pattern identification: LOW-MEDIUM (subjective)

# What This Skill Must Not Do

- Do not generate UI designs
- Do not modify analyzed project
- Do not claim visual evidence is definitive without code corroboration

# Related Skills

- ui-analyst (code-based UI analysis)
- design-system-extractor (token extraction)
