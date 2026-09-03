# Aurora Design System

Aurora is an AI-first Design System infrastructure designed to be readable by humans and AI agents.

The repository is being built incrementally so the Design System is not dependent on a single interface such as Figma.

## Structure

- `foundations/` — visual and structural foundations
- `tokens/` — machine-readable design decisions
- `components/` — component anatomy, variants, states and usage rules
- `patterns/` — reusable product and interaction patterns
- `docs/` — governance and system documentation
- `ai/` — instructions for AI agents consuming Aurora

## Build order

`Foundations → Tokens → Components → Patterns → Docs → AI Instructions`

Figma remains an interface of Aurora, not its only source of truth.
