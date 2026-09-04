# Breadcrumb Navigation

## Status

- Version: 0.1.0
- Status: draft
- Scope: core
- Category: navigation
- Confidence: high

## Purpose

Represent contextual location within a real product hierarchy and return to valid ancestors without replacing Global Navigation or Product Navigation.

Breadcrumb Navigation is a consequence of real information architecture and journey context, never a hierarchy invented from screen appearance.

## Problem

Prevent invented hierarchy, undocumented route derivation, clickable Current, and use as primary navigation.

## Evidence

### Observed Evidence

- Breadcrumbs component set 1122:153: Divider Slash/Chevron; Type Text, Text with line, Button, Account dropdowns; Desktop/Mobile; internal _Breadcrumb button base; Current=True/False; Default/Hover/Focused.
- Observed composition equivalent to Home / Settings / ... / Team, with Team Current=True.
- Breadcrumbs contract observes Dropdown menu/account breadcrumb, Avatar, Radio and icons; dimensions are not tokens or breakpoints.

### Approved Aurora Decisions

- Breadcrumbs represent existing information architecture and journey context, never invented hierarchy.
- Exactly one Current is non-navigable.
- Compactation retains Current, Nearest Ancestor and Root before Intermediate Ancestors.
- ... represents real omitted ancestors and opens a temporary surface without changing the compacted composition.
- Available space drives adaptation; numeric breakpoints are not defined.
- Keyboard operation and visible focus are required; technical HTML and ARIA remain open.

## Anatomy

- Root
- Divider
- Ancestor(s)
- Collapsed Hierarchy (...)
- Nearest Ancestor
- Current

Not every part is required in every composition.

## Hierarchy and Behavior

### Root

Root is the first relevant contextual level. It is Home only when Home is the real root. Do not insert Home only to reproduce a visual example.

### Ancestors

Ancestors are earlier real levels and are navigable only when a valid destination exists. Do not invent destinations to make them interactive.

### Current

Exactly one Current is required. It represents the current location, uses Current=True semantically and is not navigable.

### Compactation

When space is constrained, compact Intermediate Ancestors before Root, Nearest Ancestor or Current. Retention priority: Current, Nearest Ancestor, Root, Intermediate Ancestors. No maximum level count is defined.

### Collapsed Hierarchy

... represents real omitted ancestors and is not decoration. It is keyboard reachable; Enter/Space reveals omitted ancestors in a temporary surface without changing compactation. Valid omitted ancestor destinations remain navigable. Reuse Aurora Dropdown/Menu when applicable.

## Variants

Slash and Chevron are approved dividers. Text, Button, Text with line and Account dropdowns are approved types. Their selection criteria are undocumented. Divider choice does not change hierarchy, navigability, Current or compactation. Preserve product evidence or feature specification; never choose by preference.

Account dropdowns are existing visual compositions. Account switching, permissions, selected-state semantics and context switching remain undocumented and outside this Pattern v0.

## Responsive Behavior

Desktop and Mobile compositions are observed. Adapt to available space; compact before removing relevant context. Numeric breakpoints are not defined.

## Accessibility

- Navigable ancestors: keyboard reachable
- Navigable ancestors: visible focus
- Navigable ancestors: Enter activates valid destination
- Current: communicates current location
- Current: does not navigate
- Collapsed hierarchy: keyboard reachable
- Collapsed hierarchy: Enter/Space reveals omitted ancestors
- Collapsed hierarchy: temporary surface supports keyboard navigation
- Collapsed hierarchy: focus returns to ... when closed
- Focus order follows logical hierarchy.
- Assistive technology communicates contextual navigation, hierarchy order, ancestors and current location.
- HTML and ARIA attributes remain undocumented.

## Relationship with Other Patterns

Breadcrumb Navigation represents local hierarchical context and does not replace Application Shell, Global Navigation or Product Navigation.

## AI Guidance

### Must

- Represent real contextual hierarchy.
- Keep exactly one non-navigable Current.
- Navigate ancestors only with valid destinations.
- Preserve hierarchy order.
- Compact only when space requires.
- Prioritize Current, Nearest Ancestor and Root.
- Use ... only for real omitted ancestors.
- Provide keyboard equivalence and visible focus.
- Reuse Aurora components.

### Should

- Prefer full hierarchy when space permits.
- Compact only when necessary.
- Preserve established product Type and Divider.
- Keep Type and Divider consistent.

### Must Not

- Invent levels.
- Derive Breadcrumbs from URL/routes without documented rule.
- Make Current clickable.
- Replace Global or Product Navigation.
- Use ... decoratively.
- Remove levels randomly.
- Invent maximum levels or numeric breakpoints.
- Choose Type/Divider aesthetically.
- Assume Account dropdown behavior.
- Insert Home without real root.
- Invent HTML/ARIA implementation.

## Anti-patterns

- Invent levels from screen appearance.
- Use ... without omitted real ancestors.
- Make Current clickable.
- Use Breadcrumb as main menu.
- Hide ancestors without space necessity.
- Choose Chevron as more modern or Button as better on mobile.
- Map /frota/veiculos/123 without documented route mapping.
- Add account selector only because it exists in component set.

## Open Questions

1. Official Text/Button/Text with line criterion.
2. Official Slash/Chevron criterion.
3. Account dropdown semantics and behavior.
4. Official numeric breakpoints.
5. Specific ARIA implementation rules.
6. Route to breadcrumb mapping.

## Related Resources

- components/breadcrumbs.json
- components/breadcrumbs.md
- patterns/application-shell.*
- patterns/global-navigation.*
- patterns/product-navigation.*

## Version History

### 0.1.0 — Draft

Initial Breadcrumb Navigation Pattern Contract v0.
