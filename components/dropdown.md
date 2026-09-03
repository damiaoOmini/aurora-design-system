# Dropdown

Aurora Dropdown defines the menu composition used for contextual actions, account controls, searches, integrations and button/icon-triggered menus.

## Source of truth

Figma component set:

- `Dropdown menu`
- Node ID: `3281:383083`
- 28 approved variants

Machine-readable contract:

- `components/dropdown.json`

## Structure discovered on the Dropdowns page

The page contains the public `Dropdown menu` component plus internal primitives:

- `_Dropdown menu header`
- `_Dropdown menu list item`
- `_Dropdown menu item inset icon`
- `_Dropdown menu footer`
- `_Dropdown account list item`

It also contains a separate `Context menu` component set. Context Menu is not merged into this contract.

## Variant axes

Dropdown exposes two axes:

### Type

- Button simple
- Button advanced
- Button link
- Icon simple
- Icon advanced
- Search simple
- Search advanced
- Integrations
- Account button
- Account avatar
- Account card xs
- Account card sm
- Account card md
- Account breadcrumb

### Open

- False
- True

The 14 Types × 2 Open values produce exactly 28 combinations, and all 28 are represented in Figma.

## Component properties

Dropdown also exposes:

- Scrollbar visibility
- Dropdown chevron visibility

## Trigger dimensions

Observed trigger dimensions include:

| Type | Dimensions |
| --- | ---: |
| Icon simple | 20×20px |
| Icon advanced | 20×20px |
| Account avatar | 32×32px |
| Account button | 105×36px |
| Button simple | 100×36px |
| Button advanced | 100×36px |
| Integrations | 84×36px |
| Search simple | 154×36px |
| Search advanced | 154×36px |
| Account card xs | 152×36px |
| Account card sm | 168×44px |
| Account card md | 240×56px |
| Button link | 73×20px |
| Account breadcrumb | 135×28px |

These are observed component dimensions, not global Aurora sizing tokens.

## Anatomy and composition

Dropdown is a composition rather than a single primitive control.

Common structures include:

- Trigger
- Menu
- Menu items
- Header
- Footer
- Divider
- Shortcut
- Icons and text
- Supporting text
- Optional scrollbar

Nested dependencies observed include:

- Checkbox
- Avatar
- Button
- Button utility
- Toggle
- Integration icon
- Status icon
- Avatar label group
- Aurora icons

Agents should reference those component contracts instead of redefining them inside Dropdown.

## Typography

Core menu content primarily uses:

- text-xs — 12px
- text-sm — 14px
- Regular
- Medium
- Semibold

Typography is bound to Aurora body typography tokens.

## Semantic token bindings

Dropdown uses Aurora semantic tokens for backgrounds, borders, foregrounds, text, focus rings and shadows.

Important groups observed include:

- `Colors/Background/bg-primary`
- `Colors/Background/bg-primary_hover`
- `Colors/Background/bg-secondary_alt`
- `Colors/Border/border-primary`
- `Colors/Border/border-secondary`
- `Colors/Text/text-primary (900)`
- `Colors/Text/text-secondary (700)`
- `Colors/Text/text-secondary_hover`
- `Colors/Text/text-tertiary (600)`
- `Colors/Effects/Focus rings/focus-ring`
- Aurora shadow tokens

Radius bindings range from `radius-xs` through `radius-full`; spacing bindings range from `spacing-xxs` through `spacing-3xl`, depending on the nested composition.

## Open state

`Open=True` and `Open=False` are explicit component variants.

The repository may therefore generate either approved visual state. However, the Figma contract alone does not define runtime mechanics such as positioning, collision avoidance, portal behavior, dismissal or focus management.

## Context Menu

`Context menu` exists as a separate Component Set on the same Figma page.

It should not be treated as an alias for Dropdown until separately extracted and documented.

## AI usage rules

When an AI agent creates an Aurora Dropdown:

1. Use only the 14 approved Types.
2. Preserve the explicit `Open` axis.
3. All 28 Type × Open combinations are approved.
4. Reuse Dropdown's internal menu primitives rather than inventing menu-item structures.
5. Reuse Checkbox, Avatar, Button, Toggle and icon contracts when those dependencies appear.
6. Use semantic Aurora tokens instead of arbitrary colors, shadows, radii or spacing.
7. Do not treat observed trigger dimensions as global tokens.
8. Do not merge `Context menu` into Dropdown without a separate contract.
9. Do not infer keyboard navigation, focus trapping/management, dismissal, positioning, collision handling, ARIA roles or framework implementation from the visual component alone.
10. Missing behavior is a missing Design System decision, not permission to invent one.

## Status

Initial Aurora Dropdown contract extracted and documented from the approved `Dropdown menu` Component Set.