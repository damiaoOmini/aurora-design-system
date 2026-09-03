# Breadcrumbs

Breadcrumbs defines the approved Aurora breadcrumb compositions.

## Variants

- 16 variants.
- Divider: Slash, Chevron.
- Type: Text, Text with line, Button, Account dropdowns.
- Breakpoint: Desktop, Mobile.
- All Divider × Type × Breakpoint combinations are represented.

## Internal base

`_Breadcrumb button base` is an internal building block and should be reused rather than exposed as a separate public contract.

## Composition

Observed dependencies include the breadcrumb base, account/dropdown composition, Avatar, Radio and icons.

## Responsive rule

Desktop and Mobile are named variants. Figma dimensions are reference compositions and must not be converted into breakpoint thresholds.

## AI usage rules

- Use only the four approved Types and two approved Dividers.
- Reuse `_Breadcrumb button base` internally.
- Keep account-dropdown breadcrumbs within the approved component composition.
- Do not infer route-to-breadcrumb generation, truncation, overflow, hierarchy depth, navigation behavior, account-switching semantics or accessibility attributes until separately documented.