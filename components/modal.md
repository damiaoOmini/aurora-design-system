# Modal

Aurora Modal is a high-level overlay composition with 51 approved content/layout types across Desktop and Mobile.

## Source
- Figma: `Modal`
- Node: `4057:415205`
- 102 variants

## Axes
- Type: 51 approved modal compositions
- Breakpoint: `Desktop`, `Mobile`

All 51 × 2 combinations exist.

## Composition
Modal reuses `_Modal header`, `_Modal actions`, Background overlay, Buttons, Input, Checkbox, Select, Dropdown, Avatar, Badge, pagination indicators and other established Aurora components.

Observed example frames include 1440×960 on Desktop and 375×812 on Mobile. These dimensions do not define numeric responsive breakpoints.

## AI rules
1. Use only approved Modal Types.
2. Treat Desktop/Mobile as named variants, not media-query thresholds.
3. Reuse nested Aurora contracts instead of re-creating controls inside Modal.
4. Preserve Background overlay as part of the composition.
5. Do not infer focus trapping, Escape dismissal, outside-click dismissal, scroll locking, portal behavior, validation, submission or ARIA semantics from the visual contract alone.
6. Missing behavior is a missing Design System decision, not permission to invent one.

## Status
Initial Aurora Modal contract extracted from Figma.