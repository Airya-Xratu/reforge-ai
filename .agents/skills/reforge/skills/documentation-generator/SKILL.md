---
name: documentation-generator
description: >
  Generates agent handoff document from project model. Another AI agent should be able
  to continue work without re-analyzing the project.
---

# Purpose

Produce a complete context document for agent handoff.

# When This Skill Activates

- User asks for "handoff", "document", "context for another agent"
- Part of HANDOFF workflow
- Requires prior analysis

# Inputs

- `project_model` (all populated sections)

# Responsibilities

1. Summarize project model into readable document
2. Include quick reference, product snapshot, key screens
3. Include architecture summary, design system essentials
4. Include implementation plan, health scores
5. Include decision log and open questions
6. Verify completeness before generating

# Expected Output

- `reforge/agent-handoff.md`

# What This Skill Must Not Do

- Do not invent information not in project model
- Do not modify analyzed project

# Related Skills

- All other skills (reads their output)
