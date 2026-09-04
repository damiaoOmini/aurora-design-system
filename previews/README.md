# Aurora Previews

`previews/` stores visual evidence for Aurora contracts.

## Purpose

Previews help humans and AI agents verify how a documented Aurora component or pattern should look without treating screenshots as the source of truth.

## Structure

- `components/` — visual references for Component Contracts.
- `patterns/` — visual references for Pattern Contracts.

## Fidelity rule

A preview is evidence, not the Design System definition. The contract remains structured in `components/`, `patterns/`, `tokens/` and `assets/`.

If a preview conflicts with a current approved contract, the conflict must be reviewed instead of being silently resolved by approximation.

Visual previews must not be used to invent undocumented behavior, tokens, assets, variants or states.
