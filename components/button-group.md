# Button Group

Aurora Button Group composes adjacent button-like controls using the internal `_Button group base`.

## Source
- Figma: `Button group`
- Node: `1046:10171`
- 6 approved variants

## Axes
- Size: `sm`, `md`
- Icon: `False`, `Leading`, `Only`

All 2 × 3 combinations exist.

## Size
- `sm`: 36px height
- `md`: 40px height

Observed total group widths vary by Icon composition and are not global width tokens.

## Dependencies
- `_Button group base`
- Aurora icons

## Tokens
Uses semantic background, border, foreground and text tokens; `radius-md`; Aurora spacing; `text-sm` Semibold; and approved xs/skeuomorphic shadow bindings.

## AI rules
1. Use only `sm` and `md`.
2. Use only `False`, `Leading` and `Only` icon compositions.
3. All six combinations are approved.
4. Preserve 36px/40px group heights.
5. Do not promote observed group widths to global tokens.
6. Reuse the base contract instead of inventing segmented-control styling.
7. Do not infer selection logic, exclusivity, keyboard behavior or application semantics that are not documented.

## Status
Initial Aurora Button Group contract extracted from Figma.