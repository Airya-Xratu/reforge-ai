# Vision

## What Reforge Is

Reforge is an open-source AI skill system for reverse-engineering software intent.

It transforms source code analysis into product understanding — extracting features, screens, states, UX patterns, design systems, and the underlying product DNA from static code analysis.

## Why Reforge Exists

AI coding agents are powerful at writing code. They are poor at understanding existing products.

When an agent encounters a mobile app repository, it sees:

- Source files
- Dependencies
- Configuration

It does not see:

- What the product does
- Who uses it
- How users navigate
- What states exist
- What the design system looks like
- What the architecture philosophy is
- What makes this product unique

Mobile makes this worse. The agent often cannot run the application. There is no emulator, no backend, no credentials, no signing configuration.

Reorge bridges this gap through **static product archaeology**.

## Core Principle

> **Reforge doesn't clone code. Reforge reconstructs intent.**

The goal is never to copy implementation. The goal is to understand:

- What problem does this solve?
- For whom?
- How do users interact with it?
- What is essential vs incidental?
- What should survive a redesign?

## Architecture Philosophy

Reforge is not one giant prompt. It is an ecosystem of:

- **Evidence** — Observable facts from source code
- **Project Model** — Shared intermediate representation
- **Specialist Skills** — Narrow, focused analysis capabilities
- **Orchestrator** — Routes user intent to the right skills
- **Decision Model** — Records reasoning, alternatives, tradeoffs

Intelligence emerges from the interaction between these components.

## Progressive Disclosure

Reorge loads only what is needed. Asking "what features does this have?" does not load the UI analysis skill. Asking for a full redesign loads the complete pipeline.

This keeps context efficient and analysis focused.

## Mobile-First

Mobile applications are the primary use case because:

1. Mobile projects often cannot be executed by the agent
2. Static analysis is the only reliable evidence source
3. Mobile has complex platform-specific behaviors
4. Mobile UX patterns are rich and varied
5. Cross-platform reconstruction is valuable

Web and desktop support are planned but secondary.

## Open Source

Reforge is open source because:

- The Agent Skills ecosystem benefits from shared capabilities
- Community contributions improve analysis quality
- Transparency builds trust in AI-driven analysis
- Multiple agent platforms benefit from a common foundation

## Long-Term Aspiration

Reforge should eventually enable:

- An agent to receive any mobile project and produce a useful product blueprint
- Cross-platform reconstruction (Flutter → React Native → native)
- Automated redesign proposals based on UX best practices
- Continuous project health monitoring
- Knowledge sharing between agent sessions
