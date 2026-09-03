# Checkbox

Aurora Checkbox defines the core binary and indeterminate selection control represented by the approved Figma component set.

## Source of truth

Figma component set:

- `Checkbox`
- Node ID: `1097:63652`
- 72 approved variants

Machine-readable contract:

- `components/checkbox.json`

The component is built on the internal `_Checkbox base` component set.

## Variant axes

The Figma component exposes six variant axes:

- Checked: `False`, `True`
- Indeterminate: `False`, `True`
- Size: `sm`, `md`
- Type: `Checkbox`, `Radio`
- Text: `False`, `True`
- State: `Default`, `Hover`, `Focused`, `Disabled`

### Important combination rule

Those axes theoretically allow 128 combinations, but the approved Figma component set contains 72 actual variants.

AI agents and implementations must therefore **not** assume every theoretical combination is valid. Only combinations represented by the approved component set should be treated as Aurora-approved.

## Important source-model observation

Although this component set is named `Checkbox`, its `Type` axis contains both `Checkbox` and `Radio`.

This documentation preserves that Figma structure instead of silently rewriting it. Radio will be inspected separately before deciding whether the repository should expose a distinct public Radio contract.

## Component properties

In addition to the variant axes, the component exposes:

- Supporting text visibility

## Sizes

| Size | Selection control | Observed total size without/with text |
| --- | ---: | --- |
| `sm` | 16×16px | 16px / up to 344×40px |
| `md` | 20×20px | 20px / up to 344×50px |

The 344px width belongs to text-bearing examples and must not be interpreted as a fixed Checkbox width token.

## Anatomy

The recurring core is:

- `_Checkbox base`

When `Text=True`, the component can include:

- Input wrapper
- Text and supporting text wrapper
- Text
- Supporting text

Selection indicators observed in the component are:

- `check` — checked Checkbox indicator
- `minus` — indeterminate indicator

## Typography

Observed roles:

### sm

- Label: 14px Medium
- Supporting text: 14px Regular

### md

- Label: 16px Medium
- Supporting text: 16px Regular

Typography is bound to Aurora body font, text-sm/text-md, Regular/Medium and the corresponding line-height tokens.

## Semantic token bindings

### Background

- `Colors/Background/bg-brand-solid`
- `Colors/Background/bg-primary`
- `Colors/Background/bg-tertiary`

### Border

- `Colors/Border/border-primary`

### Foreground

- `Colors/Foreground/fg-white`

### Text

- `Colors/Text/text-secondary (700)`
- `Colors/Text/text-tertiary (600)`

### Focus

- `Colors/Effects/Focus rings/focus-ring`

### Shape and spacing

Observed bindings include:

- `radius-full`
- `spacing-xxs`
- `spacing-xs`
- `spacing-sm`
- `spacing-md`
- `spacing-lg`

`radius-full` appears because the same source component set also contains Radio variants. Do not infer that the visible Checkbox control itself must always use a fully rounded shape.

## States

Approved state values are:

- `Default`
- `Hover`
- `Focused`
- `Disabled`

`Checked` and `Indeterminate` are independent axes rather than State values. This distinction must be preserved by AI agents and implementations.

## AI usage rules

When an AI agent creates an Aurora Checkbox from this contract:

1. Use only `sm` and `md` sizes.
2. Preserve 16×16px for `sm` and 20×20px for `md` selection controls.
3. Use only the four approved State values.
4. Treat `Checked` and `Indeterminate` independently from interaction State.
5. Do not assume all 128 theoretical combinations exist; only 72 are approved in Figma.
6. Treat text and supporting text as optional composition around the base control.
7. Use semantic Aurora tokens instead of raw colors or arbitrary spacing.
8. Do not reinterpret `Type=Radio` until the separate Radio extraction establishes its intended public contract.
9. Do not infer form submission behavior, group selection logic, keyboard interaction, ARIA attributes or framework implementation from the visual component alone.
10. If a required behavior is absent from the contract, treat it as a missing Design System decision rather than inventing it.

## Status

Initial Aurora Checkbox contract extracted and documented from the approved Figma component set.