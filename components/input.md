# Input

Aurora Input defines the core text-entry field system used across product interfaces.

## Source of truth

Figma component set:

- `Input field`
- Node ID: `1090:57817`
- 294 approved variants

Machine-readable contract:

- `components/input.json`

The separate `Input-omnilink` component set is product-specific and is not merged into this core Aurora contract.

## Variant axes

The component exposes four variant axes:

- Size: `sm`, `md`, `lg`
- Type: 14 approved types
- Destructive: `False`, `True`
- State: `Placeholder`, `Filled`, `Focused`, `Disabled`

Approved types:

- `Default`
- `Leading dropdown`
- `Trailing dropdown`
- `Leading text`
- `Payment input`
- `Tags inner`
- `Tags outer`
- `Trailing button`
- `Password`
- `Date and time`
- `Number counter horizontal`
- `Number counter vertical`
- `OTP`
- `File upload`

### Important combination rule

The axes theoretically allow 336 combinations, but the Figma component set contains 294 actual variants.

Therefore, AI agents and implementations must **not** assume every theoretical combination exists. Only approved combinations represented by the component set should be treated as valid Aurora Input variants.

## Component properties

The component also exposes independent properties for:

- Label visibility
- Hint text visibility
- Help icon visibility
- Icon instance swap
- Required indicator (`*`)
- Leading icon visibility
- Time selector visibility

## Sizes

| Size | Core control height | Observed total component heights |
| --- | ---: | --- |
| `sm` | 36px | 86–92px |
| `md` | 40px | 92–98px |
| `lg` | 44px | 96–102px |

The total height is not a fixed input-height token. It changes according to Label, Hint/Error text and the selected complex Input Type.

## Anatomy

The recurring structural anatomy contains:

- Input with label
- Label wrapper
- Input
- Text input

Optional or type-specific anatomy can include:

- Label
- Required indicator
- Hint or error text
- Help icon
- Leading icon
- Dropdown controls
- Tags
- Trailing Button
- Password controls
- Date and time controls
- Number counters
- OTP controls
- File upload controls

The component also reuses other Aurora assets such as `Buttons/Button`, Tags and Icons. Those dependencies must be documented through their own component contracts rather than redefined inside Input.

## Typography

Observed approved text roles include:

- Label: 14/20 Medium
- Standard input content: 16/24 Regular
- Supporting text: 14/20 Regular
- Compact supporting text: 12px Regular

Bindings reference Aurora typography tokens for body font family, text-xs, text-sm, text-md, Regular, Medium, Semibold and their corresponding line heights.

## Semantic token bindings

### Background

- `Colors/Background/bg-primary`

### Borders

- `Colors/Border/border-primary`
- `Colors/Border/border-secondary`
- `Colors/Border/border-brand`
- `Colors/Border/border-error`
- `Colors/Border/border-error_subtle`

These bindings encode default, focused/brand and destructive/error visual decisions.

### Text

- `Colors/Text/text-primary (900)`
- `Colors/Text/text-secondary (700)`
- `Colors/Text/text-tertiary (600)`
- `Colors/Text/text-placeholder`
- `Colors/Text/text-brand-tertiary (600)`
- `Colors/Text/text-error-primary (600)`

### Foreground / icons

- `Colors/Foreground/fg-brand-secondary_alt`
- `Colors/Foreground/fg-error-secondary`
- `Colors/Foreground/fg-quaternary (400)`
- `Colors/Foreground/fg-success-primary`

### Shape, spacing and effects

The Input uses approved Aurora bindings including:

- `radius-sm`
- `radius-md`
- `spacing-none`
- `spacing-xxs`
- `spacing-xs`
- `spacing-sm`
- `spacing-md`
- `spacing-lg`
- `spacing-xl`
- `Colors/Effects/Shadows/shadow-xs`

## States

The core state axis defines:

- `Placeholder`
- `Filled`
- `Focused`
- `Disabled`

`Destructive=True` is a separate axis rather than a fifth State value. This distinction must be preserved when generating or implementing the component.

## Core vs product-specific Input

The Inputs page also contains `Input-omnilink`.

That component is intentionally excluded from this core contract. Product-specific or themed variants should extend or map to Aurora core without silently changing the core Input specification.

## AI usage rules

When an AI agent creates an Aurora Input:

1. Use only the three approved Sizes.
2. Use only the 14 approved Types.
3. Use `Destructive` independently from `State`.
4. Do not assume all theoretical combinations are valid; the approved set contains 294 combinations, not 336.
5. Use semantic Aurora tokens instead of raw colors or arbitrary spacing.
6. Preserve the 36px / 40px / 44px core control heights for sm / md / lg.
7. Treat Label, Hint, Help icon, Required indicator and Leading icon as explicit component properties.
8. Do not redefine nested Button, Tag or Icon behavior inside Input.
9. Keep `Input-omnilink` and other product-specific variants separate from Aurora core.
10. Do not infer validation rules, masks, allowed characters, HTML input types, keyboard behavior, ARIA attributes or framework implementation from the visual component alone.
11. If a required behavior is missing from the contract, treat it as a missing Design System decision instead of inventing it.

## Status

Initial Aurora core Input contract extracted and documented from the approved Figma component set.