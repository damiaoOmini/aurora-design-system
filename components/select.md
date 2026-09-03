# Select

Aurora Select defines the core single-selection control used across product interfaces.

## Source of truth

Figma component set:

- `Select`
- Node ID: `3281:377673`
- 90 approved variants

Machine-readable contract:

- `components/select.json`

`Multi-select` is a separate component set and is not merged into this core Select contract.

## Variant axes

The component exposes three variant axes:

- Size: `sm`, `md`, `lg`
- Type: `Default`, `Icon leading`, `Avatar leading`, `Dot leading`, `Search`, `Tags`
- State: `Placeholder`, `Default`, `Focused`, `Open`, `Disabled`

The axes produce exactly 90 combinations, and all 90 are present in the approved component set. Unlike the Input component, there is no missing combination gap in this Select contract.

## Component properties

The component also exposes independent properties for:

- Label visibility
- Hint text visibility
- Supporting text visibility
- Scroll bar visibility
- Icon instance swap
- Required indicator (`*`)
- Help icon visibility
- Shortcut visibility

## Sizes

| Size | Core control height | Closed total height | Open total height |
| --- | ---: | ---: | ---: |
| `sm` | 36px | 86px | 62px |
| `md` | 40px | 92px | 66px |
| `lg` | 44px | 96px | 70px |

Observed widths are primarily 320px, while Tags variants also use 400px. Width should therefore not be treated as a fixed global Select token.

## Anatomy

Recurring structure includes:

- Input with label
- Label wrapper
- Input
- Content
- Text and supporting text

Optional/type-specific anatomy includes:

- Label
- Required indicator
- Hint text
- Supporting text
- Help icon
- Leading icon
- Avatar
- Dot
- Search icon
- Tags
- Shortcut
- Chevron

### Open state

The `Open` state is composite and includes:

- Menu
- Menu items
- `_Select menu item`
- Scroll bar

Those subcomponents should be documented independently instead of being redefined inside Select.

## Typography

Observed text roles include:

- Label: 14/20 Medium
- Selected/value text: 16px Medium
- Supporting text: 14px or 16px Regular depending on context
- Hint text: 12px or 14px Regular
- Shortcut: 12px Medium

Bindings reference Aurora typography tokens for the body font family, text-xs, text-sm, text-md, Regular, Medium and corresponding line heights.

## Semantic token bindings

### Background

- `Colors/Background/bg-primary`
- `Colors/Background/bg-primary_hover`

### Borders

- `Colors/Border/border-primary`
- `Colors/Border/border-secondary`
- `Colors/Border/border-secondary_alt`
- `Colors/Border/border-brand`

### Text

- `Colors/Text/text-primary (900)`
- `Colors/Text/text-secondary (700)`
- `Colors/Text/text-tertiary (600)`
- `Colors/Text/text-quaternary (500)`
- `Colors/Text/text-placeholder`
- `Colors/Text/text-brand-tertiary (600)`

### Foreground

- `Colors/Foreground/fg-quaternary (400)`
- `Colors/Foreground/fg-brand-primary (600)`
- `Colors/Foreground/fg-success-secondary`

### Shape, spacing and effects

The component references:

- `radius-xs`
- `radius-sm`
- `radius-md`
- `radius-full`
- `spacing-xxs`
- `spacing-xs`
- `spacing-sm`
- `spacing-md`
- `spacing-lg`
- `Colors/Effects/Shadows/shadow-xs`
- `Colors/Effects/Shadows/shadow-lg_01`
- `Colors/Effects/Shadows/shadow-lg_02`
- `Colors/Effects/Shadows/shadow-lg_03`

## Select vs Multi-select

The same Figma page also contains `Multi-select` and its internal `_Multi-select menu item`.

Those are intentionally excluded from this contract. Single-select and multi-select behavior should not be silently merged into one machine-readable component definition.

## AI usage rules

When an AI agent creates an Aurora Select:

1. Use only the three approved Sizes.
2. Use only the six approved Types.
3. Use only the five approved States.
4. All 90 combinations of Size × Type × State are represented and may be treated as approved.
5. Preserve the 36px / 40px / 44px core control heights for sm / md / lg.
6. Use semantic Aurora tokens instead of raw colors or arbitrary spacing.
7. Treat Label, Hint, Supporting text, Help icon, Required indicator, Shortcut and Scroll bar as explicit properties.
8. Treat `Open` as a composite state that depends on menu-item and scrollbar subcomponents.
9. Keep `Multi-select` separate from core Select.
10. Do not infer filtering logic, keyboard navigation, selection persistence, async loading, ARIA attributes or framework implementation from the visual component alone.
11. If required behavior is missing, treat it as a missing Design System decision rather than inventing it.

## Status

Initial Aurora core Select contract extracted and documented from the approved Figma component set.