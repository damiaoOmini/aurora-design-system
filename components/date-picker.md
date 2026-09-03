# Date Picker

Aurora Date Picker defines approved date and available-time selection compositions.

## Public components

### Date picker dropdown
- 24 variants.
- Opened: False, True.
- Type: Dual dates, Single date, Available times.
- State: Placeholder, Active.
- Breakpoint: Desktop, Mobile.
- All combinations are represented.

### Date picker modal
- 6 variants.
- Type: Dual dates, Single date, Available times.
- Breakpoint: Desktop, Mobile.
- All combinations are represented.

## Internal components

### _Date picker menu
Six Type × Breakpoint variants. It exposes optional Pre-set ranges, Actions and Scroll bar properties.

### _Date picker list item
Six Selected × State variants using Default, Hover and Focused states.

### _Calendar cell
Twelve variants: Default, Today's date, Selected and Active × Default, Hover and Disabled. It exposes optional left connector, right connector and active dot properties.

## Composition

Observed dependencies include Button, Input field, Background overlay and icons. Reuse existing Aurora contracts rather than recreating nested controls.

## Responsive rule

Desktop and Mobile are named variants only. Observed Figma dimensions are reference compositions and must not become global breakpoint or sizing tokens.

## AI usage rules

- Keep dropdown and modal as distinct public compositions.
- Reuse the internal menu, list item and calendar-cell structures.
- Use only documented combinations and Aurora tokens.
- Do not infer date parsing, locale, timezone, minimum/maximum dates, range validation, disabled-date rules, available-time sourcing, keyboard interaction, focus management or accessibility semantics until separately documented.