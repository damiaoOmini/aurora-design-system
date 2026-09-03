# Application Shell

## Status

- Version: `0.1.0`
- Status: `draft`
- Scope: `core`
- Category: `navigation`
- Confidence: `high`

## Purpose

Define the persistent structural frame that organizes the main Aurora application environment, separating global application context, navigation and product workspace.

The shell establishes this hierarchy:

```text
Global application context
↓
Product/workspace context
↓
Feature content
```

## Problem

Without a consistent application shell, different products can recreate global navigation, mix global and local responsibilities, duplicate headers, alter workspace hierarchy and reduce predictability between modules.

The pattern exists to preserve a shared structural frame across Aurora applications.

## Evidence

The pattern is supported by recurring product evidence in the Aurora Figma source.

### Workspace with contextual notification panel

- Figma node: `19278:327`
- Observation: `Header/Hero`, `Navigation/Global` and the workspace remain present while a contextual notification panel opens.
- Confidence: high

### ERP operational workspace

- Figma node: `19471:1938`
- Observation: `Header/Hero`, `Navigation/Global`, `Breadcrumbs` and a product workspace compose the ERP experience.
- Confidence: high

### Empty workspace

- Figma node: `19920:3497`
- Observation: the shell remains unchanged while the workspace content is replaced by an `Empty state`.
- Confidence: high

### Videowall workspace

- Figma node: `19920:3853`
- Observation: the same shell structure is reused for a camera monitoring workspace.
- Confidence: high

These examples demonstrate recurrence across different product contexts rather than a single isolated visual composition.

## Anatomy

```text
Application Shell
│
├── Global Header
│
├── Global Navigation
│
└── Application Workspace
    │
    ├── Context Navigation
    │   └── Breadcrumbs when applicable
    │
    └── Feature Content
```

### Global Header

Required region. Provides persistent global application context and global actions.

`Header/Hero` is consistently observed in product examples, but does not yet have a dedicated Aurora component contract in this repository.

### Global Navigation

Required region. Provides navigation between major products, tools or application areas.

Use the existing Aurora `application-navigation` component contract.

### Application Workspace

Required region. Hosts the active product, module or feature experience.

The workspace may contain other Aurora patterns and feature-specific compositions.

### Context Navigation

Optional region. Provides orientation within the active product context, currently observed primarily through `Breadcrumbs`.

## Components

### Required

- `application-navigation`

### Optional

- `breadcrumbs`

### Observed dependency not yet contracted

- `Header/Hero`

Do not create an invented repository contract for `Header/Hero` until it is explicitly extracted and validated.

## Composition Rules

1. Global navigation must remain outside feature content.
2. The global header belongs to the shell and must not be recreated inside individual feature screens.
3. Breadcrumbs belong to workspace context and must not replace global or product navigation.
4. Feature-specific navigation must remain inside the product or workspace context.
5. The workspace may contain dashboards, tables, maps, videowalls, empty states and contextual panels without changing the shell hierarchy.
6. Contextual overlays may coexist with the shell when the underlying application context must remain available.
7. Reuse approved Aurora navigation structures before introducing custom application-level navigation.

## When to Use

Use Application Shell for authenticated Aurora application experiences that require a persistent global environment, including observed contexts such as:

- dashboards;
- ERP workspaces;
- events and operational listings;
- maps;
- monitoring experiences;
- videowalls;
- product or module workspaces inside the main application.

## When Not to Use

The following contexts have not yet been validated against this pattern:

- public pages;
- isolated authentication experiences;
- landing pages;
- standalone experiences outside the main Aurora environment.

These are current exclusions by lack of evidence, not stable Aurora rules.

## Behavior

Observed behavior is intentionally separated from undocumented behavior.

### Observed

- Global Navigation supports expanded and collapsed representations.
- Global navigation items expose interaction states in the Aurora source.
- Contextual panels can open while preserving the underlying shell.

### Undocumented

The current sources do not define:

- routing behavior;
- deep linking;
- navigation state persistence;
- session persistence;
- permission-based visibility;
- keyboard navigation model;
- focus management after navigation;
- mobile navigation behavior.

Do not infer these behaviors from visual appearance alone.

## States

### Default

Global header, global navigation and active workspace are available.

### Navigation Expanded

Global Navigation is displayed in its expanded representation.

### Navigation Collapsed

Global Navigation is displayed in its reduced representation.

### Context Overlay Open

A contextual or global panel is presented while the underlying shell remains available.

### Workspace Loading and Empty

Loading and empty states are primarily responsibilities of the active workspace or feature, not states of the shell itself.

## Responsive Behavior

### Desktop

Observed and supported by current product evidence.

### Mobile

Not yet validated.

### Tablet

Not yet validated.

### Breakpoints

No numeric breakpoint values are defined by this pattern. Existing Aurora width tokens must not be interpreted as breakpoints without explicit evidence.

## Accessibility

The shell must preserve a logical relationship between global header, navigation and workspace content.

The current product evidence does not yet specify:

- keyboard traversal order;
- focus management;
- application landmarks;
- ARIA navigation structure;
- mobile navigation accessibility behavior;
- exact accessible labels for global navigation regions.

These remain open accessibility requirements and must not be invented by AI-generated interfaces.

## Content Guidelines

- Keep global navigation labels distinct from page or workspace titles.
- Use breadcrumbs for contextual orientation, not primary application navigation.
- Keep product-specific naming and feature content inside the workspace context.

## Do

- Reuse Aurora Application Navigation.
- Preserve the hierarchy `Global Header → Global Navigation → Workspace`.
- Keep product-specific content inside the workspace.
- Use Breadcrumbs when contextual orientation is needed.
- Compose feature-specific Aurora patterns inside the workspace.
- Preserve the user's global application context when workspace content changes.

## Don't

- Create a second global navigation inside the workspace.
- Duplicate the global header inside feature content.
- Use breadcrumbs as primary application navigation.
- Allow one feature to redefine the global shell hierarchy without a system-level decision.
- Create a different application shell for each module without an explicit architecture decision.
- Invent breakpoint values, routing rules, keyboard behavior or persistence behavior.
- Replace existing Aurora navigation components with visually similar custom structures.

## Product Examples

### ERP

- Figma node: `19471:1938`
- Usage: vehicle operational workspace.

### Video Dashboard

- Figma node: `19920:2384`
- Usage: analytics and events workspace.

### Videowall

- Figma node: `19920:3853`
- Usage: configurable camera monitoring workspace.

Product examples are evidence of use. Their domain-specific logic is not part of the Core Pattern.

## AI Guidance

### Must

- Reuse Aurora Application Navigation.
- Preserve the documented shell hierarchy.
- Keep feature-specific content inside the application workspace.
- Reuse Breadcrumbs when contextual navigation is required.
- Keep global navigation outside feature composition.

### Should

- Prefer Application Shell as the structural starting point for authenticated Aurora product workspaces.
- Preserve context while feature content changes.
- Compose other validated Aurora patterns inside the workspace.

### Must Not

- Invent a new shell when this pattern satisfies the requirement.
- Recreate global navigation locally.
- Mix global navigation and product navigation responsibilities.
- Invent numeric breakpoints.
- Invent keyboard, routing or persistence behavior.
- Replace Aurora components with visually similar custom elements.

## Known Limitations

- `Header/Hero` is observed but not yet represented by a dedicated repository component contract.
- Mobile and tablet shell behavior are not validated.
- Keyboard, focus, routing and persistence contracts are incomplete.
- Accessibility landmarks are not yet documented.

## Open Questions

1. Is `Header/Hero` formally part of Aurora Core Components?
2. How should the shell behave on mobile?
3. Is Global Navigation expansion persisted?
4. What determines Expanded versus Collapsed state?
5. What is the keyboard navigation model?
6. What landmarks and ARIA structure should engineering use?
7. How does Product Navigation interact with Global Navigation?
8. Is Breadcrumb mandatory for every product screen or contextual?
9. Are global overlays allowed to cover navigation?
10. What permission rules affect global navigation visibility?

## Related Patterns

Current candidates:

- Product Navigation
- Breadcrumb Navigation
- Contextual Detail Panel
- Selection Side Panel
- Tabbed Workspace
- Workspace Utility Bar

These relationships should become repository references only after the related patterns are documented.

## Version History

### 0.1.0 — Draft

Initial contract derived from recurring product evidence in Aurora Figma sources. Structural rules are considered high-confidence; behavior, responsive and accessibility contracts remain partial.
