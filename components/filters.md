# Filters

Aurora Filters is a family of three public filtering components extracted from the approved Figma library.

## Public components

### Filters dropdown menu
- 16 variants.
- State: Default, Disabled, Focused, Hover, Open empty state, Active, Open inactive filter, Open active filters.
- Orientation: Left aligned, Right aligned.
- Optional dropdown chevron and counter badge.
- All State × Orientation combinations are represented.

### Filters slideout menu
- 6 variants.
- State: Inactive filter, Active filters, Empty state.
- Breakpoint: Desktop, Mobile.
- All combinations are represented.

### Filters bar
- 16 variants.
- Types: Dropdowns, Simple, Advanced inactive filter, Advanced active filters, Dropdowns and date picker, Date filters, Tabs and search, Tabs and date picker.
- Breakpoint: Desktop, Mobile.
- All combinations are represented.

## Composition

Observed dependencies include Button, Input field, Select, Checkbox, Tabs, Date picker, Badge, Background overlay and icons. Reuse their Aurora contracts where available.

## Responsive rule

Desktop and Mobile are approved named variants. Observed Figma frame widths are reference compositions only and must not be converted into numeric breakpoints.

## AI usage rules

- Keep dropdown menu, slideout menu and filters bar as distinct public components.
- Use only approved variants and Aurora tokens.
- Reuse nested component contracts rather than recreating controls.
- Do not infer filter query semantics, persistence, URL synchronization, result counts, date logic, apply/clear behavior or data fetching from the visual contract.