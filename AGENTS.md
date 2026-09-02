# Agent Instructions

This file guides AI coding agents contributing to Reforge itself.

## Before Changing Anything

1. Inspect repository structure (`list_directory`, `glob`)
2. Read the relevant skill's `SKILL.md`
3. Understand existing conventions — do not refactor unrelated code
4. Read `docs/concepts/` for architectural context

## When Adding a Skill

1. Define a **narrow responsibility** — one skill, one job
2. Avoid duplication with existing skills — check `skills/` directory
3. Use the contract format in `templates/skill-template.md`
4. Define: purpose, activation triggers, inputs, responsibilities, evidence, output, confidence rules
5. Update `SKILL.md` orchestrator routing table
6. Update `docs/analyzers/` or `docs/workflows/` as appropriate
7. Add the skill to `schemas/project-model.schema.yaml` if it produces new sections

## When Modifying the Project Model Schema

1. Preserve backwards compatibility where practical
2. Add new sections at the end
3. Update `examples/project-model.yaml`
4. Update `docs/concepts/project-model.md`
5. Check all skills that reference the schema

## When Modifying Documentation

1. Keep explanations concise — agents read for information, not prose
2. Use consistent terminology (see below)
3. Link related concepts
4. Include evidence classification where appropriate

## Terminology

Use these terms consistently throughout the repository:

| Term | Meaning |
|---|---|
| Reforge | The overall system |
| Project Model | Shared intermediate representation (YAML) |
| Product DNA | Characteristics that define the product |
| Evidence | Observable facts supporting conclusions |
| Evidence Graph | Relationship map between findings |
| MAS | Minimum Architectural Skeleton |
| MVC | Minimum Viable Clone |
| Skill | Self-contained analysis capability |
| Orchestrator | Root skill that routes to specialists |
| Lens | Analytical perspective (Product, UX, UI, Engineering) |
| Workflow | End-to-end user task (Understand, Redesign, etc.) |

## General Rule

> Do not make Reforge smarter by making prompts longer. Make Reforge smarter by making its model, evidence, orchestration, and boundaries better.
