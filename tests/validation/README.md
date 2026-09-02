# Validation Tests

This directory contains validation tests for the Reforge repository itself.

## What's Validated

- Repository structure integrity
- SKILL.md frontmatter completeness
- Project Model schema validity
- Documentation links
- Terminology consistency
- No duplicate skill responsibilities

## Running

The validation runs automatically via GitHub Actions on every push and PR.

To run locally:

```bash
# Check structure
ls .agents/skills/reforge/SKILL.md
ls .agents/skills/reforge/skills/*/SKILL.md

# Validate YAML
python3 -c "import yaml; yaml.safe_load(open('.agents/skills/reforge/schemas/project-model.schema.yaml'))"

# Check skill count
ls -d .agents/skills/reforge/skills/*/ | wc -l
```
