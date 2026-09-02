# Contributing to Reforge

Thank you for considering contributing to Reforge.

## Ways to Contribute

### Skills

Add or improve specialist analysis skills.

1. Check existing skills in `.agents/skills/reforge/skills/`
2. Use the contract format in `templates/skill-template.md`
3. Define narrow responsibility — one skill, one job
4. Define evidence sources, confidence rules, expected output
5. Open a PR with description of what the skill analyzes and why

### Analyzers

Implement deterministic analysis scripts in `.agents/skills/reforge/scripts/`.

- Framework detection
- Dependency extraction
- Route extraction
- Asset cataloging
- Dead code detection

### Documentation

Improve explanations in `docs/`.

- Concept documentation
- Workflow descriptions
- Analyzer guides
- Examples

### Fixtures

Add test fixtures in `tests/fixtures/`.

- Real-world project structures (anonymized)
- Edge cases
- Contradictory projects

### Bug Reports

Open an issue using the Bug template.

### Feature Requests

Open an issue using the Feature template.

### Design Discussions

Open a Discussion for architectural decisions before implementing.

## Development Process

1. Fork the repository
2. Create a feature branch
3. Make changes following existing conventions
4. Validate structure with the CI workflow
5. Submit a pull request

## Quality Standards

- Every skill must have a complete SKILL.md contract
- Every finding must trace to evidence
- No two skills should have nearly identical responsibilities
- Documentation must be concise and accurate
- The Project Model schema must remain backwards-compatible when possible

## Code of Conduct

See [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).
