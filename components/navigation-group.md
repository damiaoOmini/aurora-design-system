# Navigation/Group

## Status
- Version: `0.1.0`
- Status: `draft`
- Scope: `core`
- Confidence: `high`
- Figma component set: `19257:2592`

## Purpose
`Navigation/Group` composes one Level 1 navigation item with its Level 2 descendants.

## Variants
### Expanded=False
- Node: `19257:2555`
- Size: `348 × 48`
- Contains one `Navigation/Item` with `Level=1` and `Has children=True`.

### Expanded=True
- Node: `19257:2563`
- Size: `348 × 192`
- Vertical composition with gap `0`.
- Contains the Level 1 parent followed by Level 2 descendants.

Observed example:
- Parent: `Cadastros`
- Children: `Veículos`, `Motoristas`, `Empresas`

## Composition rules
- Parent must use `Navigation/Item Level=1` with `Has children=True`.
- Descendants use `Navigation/Item Level=2`.
- Expanded=False renders only the parent.
- Expanded=True renders the parent followed by descendants.
- Level 2 indentation is defined by `Navigation/Item`; consumers must not recreate indentation with arbitrary wrappers.
- The current source supports Level 1 → Level 2 only.

## Dependencies
- `Navigation/Item`
- `chevron-down`
- Aurora Global Navigation icons

## AI fidelity rules
Use the approved variants and existing Navigation/Item instances. Do not create orphan Level 2 items, invent Level 3+, replace the chevron/iconography with substitutes, or approximate a missing hierarchy.

If required dependencies are unavailable, report the gap rather than drawing an alternative group.