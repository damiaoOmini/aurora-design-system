# Tooltip

Aurora Tooltip provides compact contextual information with optional supporting text and seven approved arrow placements.

## Source
- Figma: `Tooltip`
- Node: `1052:489`
- 14 variants

## Axes
- Supporting text: False, True
- Arrow: None, Bottom left, Bottom right, Left, Right, Bottom center, Top center

All 2 × 7 combinations exist.

## Property
- Main tooltip text is editable text content.

## Tokens
Tooltip uses `bg-primary-solid`, white primary text, the tooltip-specific supporting-text token, approved large shadow layers, `radius-md`, Aurora spacing and text-xs typography.

## Related component
`Help icon` exists separately on the Tooltips page and is not merged into this Tooltip contract.

## AI rules
1. Use only the seven approved Arrow positions.
2. Preserve Supporting text as an independent axis.
3. Do not treat observed dimensions as fixed Tooltip size tokens.
4. Keep Help icon separate.
5. Do not infer trigger event, delays, collision handling, portal behavior, hover persistence, keyboard behavior or ARIA description semantics.

## Status
Initial Aurora Tooltip contract extracted from Figma.