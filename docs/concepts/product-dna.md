# Product DNA

## What It Is

Product DNA represents the characteristics that define a product beyond its source code.

If you rebuilt the product from scratch in a different framework, Product DNA is what should survive.

## Why It Matters

Implementation changes. Frameworks change. Design trends change.

But certain things are fundamental to the product:

- How users interact with it
- What the visual language communicates
- What the core workflow accomplishes
- What makes it different from alternatives

## Categories

### Interaction DNA

How users physically interact with the product:

- Task-oriented vs exploratory
- Fast completion vs deep engagement
- Swipe-first vs tap-first
- Minimal modals vs guided flows

### Visual DNA

What the visual design communicates:

- Professional vs playful
- Dense vs spacious
- Data-first vs content-first
- Color-coded vs monochrome

### UX DNA

How the experience feels:

- Progressive disclosure vs everything visible
- Low friction vs guided
- Undo over confirm
- Offline capable

### Product DNA

What category the product belongs to:

- Utility vs entertainment
- Individual vs social
- Free vs paid
- Personal vs professional

## Usage

When redesigning, Product DNA tells you what to preserve:

```yaml
product_dna:
  what_must_survive:
    - "Speed — core flow must be fast"
    - "Swipe interactions — users expect them"
    - "Color-coded status — visual scanning depends on it"
```

## Extraction

Product DNA is inferred from consistent patterns across the codebase. It is MEDIUM confidence — requiring interpretation of multiple observations.
