# Navigation/Global

## Status
- Version: `0.1.0`
- Status: `draft`
- Scope: `core`
- Confidence: `high`
- Figma component set: `19257:2729`

## Purpose
`Navigation/Global` is Aurora's persistent global application navigation component. It provides two approved visual compositions: expanded and collapsed.

## Variants
### Expanded=True
- Node: `19257:2593`
- Size: `380 × 1108`
- Vertical layout
- Gap: `8px`
- Padding: `16px`

Anatomy:
1. Brand
2. Search
3. Navigation content
4. Utilities

Brand:
- `348 × 64`
- padding `12px`
- gap `12px`
- `menu-01` — `24 × 24`
- `Brand/Logo/Gestor`, `Appearance=Inverse` — `66 × 21`

Search:
- `348 × 48`
- padding `12px`
- gap `12px`
- radius `8px`
- `search-md` — `24 × 24`
- label `Pesquisar` — `14px / 20px`

Navigation content:
- `348 × 828`
- composed from `Navigation/Item` and `Navigation/Group`

Utilities:
- `348 × 112`
- includes `Configurações` as a Navigation Item
- includes `User profile` at `348 × 64`

### Expanded=False
- Node: `19257:2690`
- Size: `56 × 1108`
- Vertical layout
- Gap: `8px`
- Padding: `16px 4px`

Anatomy remains Brand, Search, Navigation content and Utilities, but it is a dedicated collapsed composition.

- Brand: `48 × 48`, menu icon only
- Search: `48 × 48`, search icon only
- Navigation content: dedicated `48 × 48` Navigation icon frames
- Utilities: settings icon + `User profile`, both `48 × 48`

**Important:** collapsed navigation must not be implemented as the expanded component with labels merely hidden. The Figma source defines a distinct composition.

## Dependencies
- `Navigation/Item`
- `Navigation/Group`
- `menu-01`
- `search-md`
- `Brand/Logo/Gestor`
- Aurora Global Navigation icon components
- User profile

## Token usage
The Figma component uses bound Aurora variables for its blue navigation background, white foregrounds, text and interaction-state colors. Consumers must preserve semantic token bindings where known instead of substituting visually similar hard-coded values.

## Component boundary
This contract describes component structure and visual variants. Routing, authorization, state persistence, keyboard behavior and responsive transformations belong to the relevant Pattern, accessibility specification or product logic when documented.

## AI fidelity rules
An AI consuming this contract must use the approved component structure and assets. It must not introduce an external OMNILINK header, replace icons with letters or emoji, remove the search or utilities from the expanded composition, or reduce the collapsed composition to hidden labels.

If a required asset, token or property is unavailable to the generation environment, the agent must stop and report the missing dependency instead of creating a visually approximate substitute.

## Source of truth
This contract was extracted directly from the Aurora Figma component set. Visual generation is permitted only when this contract, its dependencies, required tokens and required assets are all available.