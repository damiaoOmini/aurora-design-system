# Pagination

Aurora Pagination defines page- and card-level navigation compositions built from reusable pagination number and button-group bases.

## Source
- Figma: `Pagination`
- Node: `1115:68622`
- 26 approved variants

## Axes
- Type: 10 approved compositions
- Shape: `Square`, `Circle`
- Breakpoint: `Desktop`, `Mobile`

The theoretical Cartesian product is 40 combinations, but only 26 exist in Figma. Agents must use only approved combinations.

## Types
Approved Type values:
- Page default
- Page minimal center aligned
- Card minimal right aligned
- Card advanced
- Card advanced center aligned
- Card minimal left aligned
- Card minimal center aligned
- Card default
- Card button group right aligned
- Card button group left aligned

## Property
- Select dropdown visibility

## Composition
Internal bases:
- `_Pagination number base`
- `_Pagination button group base`

Dependencies include Button, Select, Input and navigation icons.

## Responsive variants
Observed Page frames: 1216×56px Desktop and 343×52px Mobile.
Observed Card frames: 1216×64px Desktop and 375×60px Mobile.

These are example frames, not responsive breakpoint thresholds or global component widths.

## AI rules
1. Use only the 26 combinations represented by Figma.
2. Do not assume all Type × Shape × Breakpoint combinations exist.
3. Preserve Square/Circle only where an approved combination exists.
4. Treat Desktop/Mobile as named variants; never infer numeric breakpoints from frame widths.
5. Reuse `_Pagination number base`, `_Pagination button group base`, Button, Select and Input contracts.
6. Do not infer page-count calculations, URL/state management, loading, keyboard behavior or accessibility semantics that are not separately documented.

## Status
Initial Aurora Pagination contract extracted from Figma.