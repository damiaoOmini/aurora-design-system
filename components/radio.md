# Radio

Aurora Radio defines the selectable item system used inside Radio Groups.

## Source of truth

Figma component set:

- `Radio group item`
- Node ID: `124:2838`
- 144 approved variants

Related composition component:

- `Radio group`
- Node ID: `1142:87213`

Machine-readable contract:

- `components/radio.json`

## Why Radio is documented separately from Checkbox

The Checkbox source component contains `Type=Radio`, but Aurora also has dedicated `Radio group item` and `Radio group` component sets.

The Radio system adds composition, breakpoint behavior and richer item types that are not represented by Checkbox alone. For that reason, the repository exposes Radio as a distinct public contract while preserving the fact that both systems reuse the internal `_Checkbox base`.

## Variant axes

`Radio group item` exposes:

- Selected: `False`, `True`
- Size: `sm`, `md`
- Type: `Radio button`, `Checkbox`, `Icon simple`, `Icon card`, `Avatar`, `Payment icon`
- State: `Default`, `Hover`, `Focused`
- Breakpoint: `Mobile`, `Desktop`

These axes produce exactly 144 combinations, and all 144 are present in Figma.

## Component property

The component exposes:

- Badge visibility

## Sizes

The reusable selection control preserves the same internal base sizing seen in Checkbox:

| Size | Selection control |
| --- | ---: |
| `sm` | 16×16px |
| `md` | 20×20px |

The overall Radio Group Item can be much larger because several Types are card-like compositions.

Observed widths include 343px and 768px, associated with Mobile/Desktop layouts and examples. They are not fixed global width tokens.

## Types

### Radio button

Standard Radio selection item.

### Checkbox

A Checkbox-flavored item can participate in the same Radio Group Item composition system. This is source structure and should not be interpreted as proof that Checkbox and Radio have identical selection semantics.

### Icon simple

Selection item with icon-based supporting composition.

### Icon card

Larger card-style selectable item.

### Avatar

Selectable item composed with Avatar content.

### Payment icon

Selectable item composed with payment-method visuals and richer supporting content.

## Anatomy

Shared internal control:

- `_Checkbox base`

Common composition can contain:

- Content
- Text
- Supporting text
- Subtext

Type-specific dependencies include:

- Featured icon
- `Buttons/Button`
- Avatar
- Payment method icon
- Badge
- Dot
- Icons
- Pricing content

The Radio contract references those components instead of redefining their internal contracts.

## Typography

Because Radio Group Item includes both simple rows and rich cards, a broader typography range is legitimately used than in the standalone Checkbox.

Observed bound scales include:

- text-xs
- text-sm
- text-md
- text-lg
- display-sm
- display-md

Weights include Regular, Medium and Semibold.

## Semantic token bindings

### Background

- `Colors/Background/bg-brand-solid`
- `Colors/Background/bg-primary`

### Borders

- `Colors/Border/border-primary`
- `Colors/Border/border-secondary`
- `Colors/Border/border-brand`

### Text

- `Colors/Text/text-secondary (700)`
- `Colors/Text/text-tertiary (600)`
- `Colors/Text/text-brand-secondary (700)`

### Foreground

- `Colors/Foreground/fg-secondary (700)`
- `Colors/Foreground/fg-white`

### Focus and effects

- `Colors/Effects/Focus rings/focus-ring`
- `Colors/Effects/Shadows/shadow-xs`
- `Colors/Effects/Shadows/shadow-skeumorphic-inner`
- `Colors/Effects/Shadows/shadow-skeumorphic-inner-border`

### Radius and spacing

Observed bindings range from `radius-xs` through `radius-full` and from `spacing-none` through `spacing-2xl`, reflecting both compact controls and card-style Radio Group Items.

## Breakpoint axis

Radio explicitly encodes:

- `Mobile`
- `Desktop`

This is different from the Layout foundation, where no global numeric breakpoint thresholds were extracted.

Therefore, agents may use the two named Radio breakpoint variants, but must **not invent numeric breakpoint values** such as `768px` unless a separate Aurora decision defines them.

## Radio group relationship

`Radio group item` is the selectable item contract.

`Radio group` is the higher-level composition that organizes multiple items. This first Radio documentation records that dependency but does not duplicate or infer group behavior that has not yet been separately extracted.

## AI usage rules

When an AI agent creates Aurora Radio UI:

1. Use only `sm` and `md` sizes.
2. Preserve 16×16px and 20×20px selection-control sizes.
3. Use only the six approved Types.
4. Use only `Default`, `Hover` and `Focused` states.
5. Use only the `Mobile` and `Desktop` breakpoint labels.
6. All 144 Size × Type × State × Selected × Breakpoint combinations are represented and may be treated as approved.
7. Keep Radio as a distinct public contract even though it shares `_Checkbox base` with Checkbox.
8. Reuse Button, Avatar, Badge and other nested component contracts instead of redefining them.
9. Do not infer numeric breakpoints from example widths.
10. Do not infer single-selection enforcement, keyboard navigation, form behavior, ARIA semantics or framework implementation from the visual component alone.
11. Missing behavior is a missing Design System decision, not permission to invent one.

## Status

Initial Aurora Radio contract extracted from `Radio group item`; `Radio group` is recorded as the related higher-level composition.