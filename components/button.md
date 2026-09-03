# Button

Aurora Button is the primary action component for triggering user actions in product interfaces.

## Source of truth

Figma component set:

- `Buttons/Button`
- Node ID: `3287:427074`
- 200 approved variants

Machine-readable contract:

- `components/button.json`

## Variant axes

The component set defines four variant axes:

- Size: `xs`, `sm`, `md`, `lg`, `xl`
- Hierarchy: `Primary`, `Secondary`, `Tertiary`, `Link color`, `Link gray`
- State: `Default`, `Hover`, `Focused`, `Disabled`, `Loading`
- Icon only: `False`, `True`

Do not introduce additional Button hierarchies, states or sizes without an explicit Aurora decision.

## Component properties

The Button also exposes:

- Leading icon visibility
- Trailing icon visibility
- Leading icon instance swap
- Trailing icon instance swap
- Loading text visibility

These properties are separate from the four variant axes.

## Sizes

| Size | Standard height | Link height | Standard padding | Icon-only size | Typography |
| --- | ---: | ---: | --- | ---: | --- |
| `xs` | 32px | 20px | 6px × 10px | 32px | Text sm / Semibold |
| `sm` | 36px | 20px | 8px × 12px | 36px | Text sm / Semibold |
| `md` | 40px | 20px | 10px × 14px | 40px | Text sm / Semibold |
| `lg` | 44px | 24px | 10px × 16px | 44px | Text md / Semibold |
| `xl` | 48px | 24px | 12px × 18px | 48px | Text md / Semibold |

Link hierarchies intentionally do not use the standard button container padding.

Icon-only variants remain square at each approved size.

## Shape and spacing

The standard button container uses `radius-md` (8px).

The component also references `radius-xs` in specific internal variants. This should not be generalized to all Buttons without matching the approved Figma variant.

Spacing bindings used by the component include:

- `spacing-xs`
- `spacing-sm`
- `spacing-md`
- `spacing-lg`
- `spacing-xl`

## Typography

Approved typography bindings include:

- `Font family/font-family-body`
- `Font size/text-sm`
- `Font size/text-md`
- `Font weight/semibold`
- `Line height/text-sm`
- `Line height/text-md`

Sizes `xs`, `sm` and `md` use 14/20 Semibold.

Sizes `lg` and `xl` use 16/24 Semibold.

## Semantic color bindings

The Button is bound to Aurora semantic color tokens rather than raw primitive colors.

Observed bindings include:

### Background

- `Colors/Background/bg-brand-solid`
- `Colors/Background/bg-brand-solid_hover`
- `Colors/Background/bg-primary`
- `Colors/Background/bg-primary_hover`

### Border and effects

- `Colors/Border/border-primary`
- `Colors/Effects/Focus rings/focus-ring`
- `Colors/Effects/Shadows/shadow-xs`
- `Colors/Effects/Shadows/shadow-skeumorphic-inner`
- `Colors/Effects/Shadows/shadow-skeumorphic-inner-border`

### Text

- `Colors/Text/text-white`
- `Colors/Text/text-brand-secondary (700)`
- `Colors/Text/text-brand-secondary_hover`
- `Colors/Text/text-secondary (700)`
- `Colors/Text/text-secondary_hover`
- `Colors/Text/text-tertiary (600)`
- `Colors/Text/text-tertiary_hover`

## AI usage rules

When an AI agent creates an Aurora Button:

1. Use only the approved Size, Hierarchy, State and Icon-only values.
2. Use semantic Aurora color tokens; do not replace them with raw HEX values.
3. Use the approved typography and dimensions for the selected size.
4. Preserve square dimensions for icon-only variants.
5. Do not infer additional visual states or hierarchies.
6. Do not infer application behavior, accessibility semantics or framework implementation from the Figma component alone.
7. If a required Button behavior is not represented by the approved contract, treat it as a missing Design System decision rather than inventing one.

## Status

Initial component contract extracted and documented from the approved Aurora Figma component set.
