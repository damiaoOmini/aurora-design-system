# Product Navigation

**Version:** 0.1.0  
**Status:** Draft  
**Scope:** Core  
**Category:** Navigation  
**Confidence:** High

## Purpose

Define how navigation inside an active product or module is organized within the Application Shell while keeping product-level destinations separate from global application navigation.

The pattern establishes the hierarchy:

```text
Global Navigation
↓
Selects product / module

Product Navigation
↓
Navigates inside the active product / module
```

## Problem

Without a shared Product Navigation pattern, modules can create inconsistent sidebars, mix global and local destinations, misuse submenus, lose active-context clarity, or recreate global navigation inside feature workspaces.

## Evidence

### Figma — Product navigation components

**Node:** `19342:543`

Observed:

- `Navigation / Product item`
- `Navigation / Product menu`
- `Navigation / Product submenu item`
- Default state
- Hover state
- Focused state
- Active state
- Disabled state
- Expanded menu
- Collapsed menu

Confidence: **High**.

### Figma — ERP workspace

**Node:** `19471:1938`

Product navigation is composed inside the ERP application workspace while Global Navigation remains structurally separate.

Confidence: **High**.

## Anatomy

```text
Product Navigation
│
├── Product Identity (optional)
│
├── Product Item
│
├── Product Menu (optional)
│   └── Product Submenu Item
│
└── Active Context
```

### Product Identity

Identifies the active product or module when required by the product composition.

Its mandatory status has not yet been established.

### Navigation Items

Provide direct navigation to primary destinations inside the active product.

### Expandable Groups

Group related destinations when a meaningful secondary hierarchy exists.

### Submenu Items

Represent destinations belonging to an expandable Product Menu.

## Components

### Contracted dependency

- `application-navigation`

### Observed Figma dependencies

- `Navigation / Product item`
- `Navigation / Product menu`
- `Navigation / Product submenu item`

These observed elements do not currently have individual component contracts in the Aurora repository. Their presence here must not be interpreted as independent documented component contracts.

## Composition Rules

### Product Navigation belongs to the active product

```text
Application Shell
│
├── Global Navigation
│
└── Workspace
    └── Product Navigation
```

Product Navigation must remain structurally separate from Global Navigation.

### Keep global and product destinations separate

Global Navigation changes the major application or product context.

Product Navigation changes destinations inside the currently active product or module.

### Direct destinations use Product Item

Use a Product Item when the destination does not require a secondary hierarchy.

### Hierarchical destinations use Product Menu

Use Product Menu only when a meaningful group of secondary destinations exists.

```text
Product Menu
└── Product Submenu Item
```

A Product Submenu Item must not appear independently at the first navigation level.

### Active and Expanded have different meanings

```text
Active
= current destination

Expanded
= navigation group is open
```

Expanded state must not be used as a substitute for Active state.

### Prefer shallow hierarchy

Use the shallowest hierarchy that accurately represents the product information architecture.

Additional levels must not be invented without evidence or an explicit system decision.

## When to Use

Use Product Navigation when an active product contains multiple areas, pages or functions that need persistent navigation within the same product context.

It is appropriate when destinations require a shallow parent-child hierarchy or when navigation should remain available while feature content changes.

## When Not to Use

Do not use Product Navigation:

- to switch between global products or tools;
- as breadcrumb navigation;
- as tabs for switching views inside the same content surface;
- for transient actions;
- for filters;
- for modal flows;
- for sequential process steps.

## Behavior

### Observed

- Item activation
- Group expansion
- Default
- Hover
- Focused
- Active
- Disabled
- Expanded
- Collapsed

### Undocumented

The available evidence does not define:

- routing behavior;
- expansion persistence;
- exclusive versus simultaneous group expansion;
- permission filtering;
- complete keyboard behavior;
- focus management after navigation;
- deep linking.

These behaviors must not be invented by consumers of this pattern.

## States

| State | Applies | Notes |
| --- | --- | --- |
| Default | Yes | Base navigation state |
| Hover | Yes | Observed in Figma |
| Focused | Yes | Observed in Figma |
| Active | Yes | Represents current destination |
| Disabled | Yes | Observed in Figma |
| Expanded | Product Menu | Group is open |
| Collapsed | Product Menu | Group is closed |

## Responsive Behavior

Desktop usage is observed.

Mobile and tablet behavior have not yet been validated.

No numeric breakpoint values are defined by this pattern.

Do not invent drawer behavior, mobile collapse rules or breakpoint thresholds.

## Accessibility

Visible Focused states are present in the observed Figma components.

The semantic hierarchy should reflect the visual hierarchy between items, groups and submenu items.

The following remain undocumented:

- complete keyboard navigation model;
- `aria-current` usage;
- `aria-expanded` usage;
- submenu semantics;
- focus management after navigation.

These require explicit accessibility validation before becoming stable Aurora rules.

## Content Guidelines

Navigation labels should represent destinations in the product information architecture rather than actions.

Use consistent labels for the same destination across screens of the same product.

## Do

- Keep Product Navigation inside the active product workspace.
- Separate Global Navigation from Product Navigation.
- Reuse Aurora navigation elements.
- Use Product Item for direct destinations.
- Use Product Menu when meaningful hierarchy exists.
- Keep submenu items under their parent Product Menu.
- Maintain a clear Active destination.
- Keep Active and Expanded conceptually separate.
- Prefer shallow information architecture.

## Don't

- Mix global products and local destinations at the same navigation level.
- Create submenu items without a parent group.
- Use navigation items as action buttons such as Export or Submit.
- Add hierarchy levels without evidence.
- Treat Expanded as Active.
- Invent mobile behavior.
- Invent routing or persistence rules.
- Invent permission behavior.
- Replace Aurora navigation elements with custom visually similar controls.

## Product Examples

### ERP

**Figma node:** `19471:1938`

Product Navigation is used to navigate between ERP areas while remaining inside the global application shell.

The ERP-specific destinations are product content and are not part of the Core Pattern definition.

## AI Guidance

### Must

- Keep Product Navigation inside the active product workspace.
- Separate Global Navigation from Product Navigation.
- Reuse Aurora navigation elements.
- Use Product Item for direct destinations.
- Use Product Menu only when secondary hierarchy exists.
- Keep submenu items under their documented parent.
- Preserve Active and Expanded as separate states.

### Should

- Prefer the shallowest hierarchy that represents the product architecture correctly.
- Keep labels aligned with product information architecture.
- Preserve a clear active destination.
- Reuse the same navigation structure across screens of the same product.

### Must Not

- Invent new navigation levels.
- Mix global products with local destinations.
- Use navigation items as buttons for actions.
- Treat Expanded state as Active state.
- Invent mobile behavior.
- Invent routing, persistence or permission rules.
- Replace Aurora navigation elements with custom visually similar controls.

## Known Limitations

The current Pattern is strongly supported for structure and visual states but only partially documented for behavior, responsiveness and accessibility.

The observed Product Item, Product Menu and Product Submenu Item elements are not yet represented as individual Aurora repository component contracts.

## Open Questions

1. Is Product Identity mandatory for every product?
2. Can Product Menu itself be a destination?
3. Can multiple Product Menus remain expanded simultaneously?
4. Is expansion state persisted?
5. What determines the default expanded group?
6. How should Active state propagate to a parent group?
7. What is the keyboard navigation model?
8. What ARIA semantics should be used for expandable groups?
9. How does Product Navigation behave on Mobile?
10. How are permission-restricted destinations handled?
11. Is there a maximum supported hierarchy depth?
12. Should Product Item, Product Menu and Product Submenu Item receive individual component contracts?

## Related Patterns

- Application Shell
- Breadcrumb Navigation
- Tabbed Workspace
- Workspace Utility Bar

## Version History

### 0.1.0 — Draft

Initial Pattern contract based on Aurora Figma navigation components and observed ERP product usage.
