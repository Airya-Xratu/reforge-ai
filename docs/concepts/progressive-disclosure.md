# Progressive Disclosure

## Principle

Load only what the user needs. Do not load every skill for every task.

## How It Works

The orchestrator receives the user's request, determines which workflows are relevant, and loads only those skills.

## Examples

| User Request | Skills Loaded |
|---|---|
| "What features does this have?" | project-archaeologist, feature-mapper, screen-analyzer |
| "Extract the design system" | design-system-extractor, ui-analyst |
| "Full analysis" | All skills via UNDERSTAND workflow |
| "Add a search feature" | project-archaeologist, feature-mapper, feature-planner, impact-analyzer |
| "Analyze this Flutter project" | mobile-analyzer → flutter-forensics + mobile-ux-forensics |

## Why It Matters

- Reduces context consumption
- Focuses analysis on relevant areas
- Prevents information overload
- Enables incremental analysis

## Incremental Analysis

When analyzing one feature, screen, or flow:
1. Load project-archaeologist for fingerprint only
2. Load relevant domain skill
3. Write to relevant project model sections
4. Skip full pipeline (contradictions, health, etc.)
