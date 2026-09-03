# Table

Aurora Table is a composed data-display system built from reusable table cells, header cells and supporting components.

## Source
- Figma: `Table`
- Node: `1227:110587`
- 16 approved variants

## Axes
- Example: `Veículos`, `Alertas`, `Dispositivos`, `Relatórios`
- Breakpoint: `Desktop`, `Mobile`
- Dividers: `Divider line`, `Alternating fills`

All 4 × 2 × 2 combinations exist.

## Composition
Public subcomponents observed:
- `Table header cell`
- `Table cell`
- `Table cell lead action`

Internal support:
- `_Table header label`

Common dependencies include Badge, Avatar, Checkbox, Button, Dropdown, Pagination, Select, Progress bar, Filters bar and icons.

## Responsive variants
Desktop examples are observed at 1216px and Mobile examples at 375px. These are reference frame widths only. They do **not** define Aurora breakpoint thresholds or global table widths.

## Dividers
Two approved visual strategies exist:
- Divider line
- Alternating fills

## AI rules
1. Treat the four Example values as approved reference compositions, not business-domain requirements for every table.
2. Reuse Table cell and Table header cell contracts instead of inventing cell styling.
3. Reuse nested component contracts such as Checkbox, Badge, Button, Dropdown, Pagination and Select.
4. Use only the two approved divider strategies.
5. Treat Desktop/Mobile as named variants only; do not infer numeric breakpoints.
6. Do not infer sorting, filtering, selection, pagination, sticky columns, resizing, keyboard navigation or data semantics from the visual component alone.

## Status
Initial Aurora Table contract extracted from Figma.