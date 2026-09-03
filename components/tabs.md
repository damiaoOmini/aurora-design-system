# Tabs

Aurora Tabs contains separate Horizontal and Vertical tab compositions built from `_Tab button base`.

## Horizontal tabs
Figma node: `1118:69893` — 40 variants.

Axes:
- Type: Button brand, Underline, Button gray, Button border, Button minimal
- Size: sm, md
- Full width: False, True
- Breakpoint: Desktop, Mobile

All 5 × 2 × 2 × 2 combinations exist.

Observed container widths include 1280px for Desktop examples and 343px for Mobile examples. These are example frame widths, **not responsive breakpoint thresholds**.

## Vertical tabs
Figma node: `1397:9880` — 20 variants.

Axes:
- Type: Button primary, Line, Button gray, Button border, Button minimal
- Size: sm, md
- Breakpoint: Desktop, Mobile

All 5 × 2 × 2 combinations exist.

Mobile examples are observed at 343px wide. This does not establish a 343px breakpoint.

## Dependencies
- `_Tab button base`
- Badge
- Select
- Aurora icons

## Tokens
Tabs use semantic Aurora backgrounds, borders, foregrounds and text; utility neutral tokens; approved shadows; radius tokens; spacing tokens; and text-xs/text-sm/text-md typography.

## AI rules
1. Keep Horizontal and Vertical Tabs as distinct compositions.
2. Use only the approved Type and Size values.
3. All documented Cartesian combinations exist.
4. Preserve `Full width` only on Horizontal Tabs.
5. Treat Desktop/Mobile as named variants, not numeric media-query definitions.
6. Never infer a breakpoint from the observed 1280px or 343px frames.
7. Reuse `_Tab button base`, Badge, Select and icon contracts where applicable.
8. Do not invent switching behavior, overflow/scroll logic, keyboard navigation, ARIA roles or routing semantics.

## Status
Initial Aurora Horizontal and Vertical Tabs contracts extracted from Figma.