# Global Navigation

## Status

- **Version:** 0.1.0
- **Status:** Draft
- **Scope:** Core
- **Category:** Navigation
- **Confidence:** High

## Purpose

Define the persistent highest-level navigation of an Aurora application. Global Navigation gives access to products, modules or major application contexts while remaining separate from product-local navigation.

## Problem

Without a dedicated contract, teams or AI agents may recreate the global navigation, mix global and local destinations, invent unsupported hierarchy or responsive behavior, or treat application infrastructure as feature-owned behavior.

## Evidence

- **Figma `19240:24569` — Global Navigation V2:** Navigation/Item Level 1 and Level 2; Default, Hover, Active, Focus and Disabled states; Navigation/Group Expanded true/false; Navigation/Global Expanded true/false.
- **Figma `19278:327` — Notifications Open:** Header/Hero, Navigation/Global and workspace remain part of the Application Shell while a notification panel overlays the workspace.
- **Figma `19471:1938` — ERP:** confirms Global Navigation in the shell and a separate Product Navigation inside the ERP workspace.
- **DIF-guided Aurora decision:** explicit expansion control, expanded first access, user preference persistence, independent group expansion, separation of expansion/navigation actions, parent-context handling for active children, authorization-driven availability, fixed Core ordering, keyboard accessibility requirements and future individual contracts for the observed navigation components.

Observed dimensions such as **380 px expanded** and **56 px collapsed** describe component states. They are not viewport breakpoints.

## Anatomy

```text
Global Navigation
│
├── Global Navigation Container
├── Explicit Expand / Collapse Control
├── Navigation Item — Level 1
├── Navigation Group
│   └── Navigation Item — Level 2
└── Active Context
```

## Components

Required contract:

- `application-navigation`

Observed Aurora dependencies:

- `Navigation/Global`
- `Navigation/Group`
- `Navigation/Item`

These observed dependencies should receive individual component contracts in a future component pass. The Pattern does not duplicate their visual token definitions.

## Composition Rules

1. Global Navigation belongs to `Application Shell` and must not be recreated by individual features.
2. Global Navigation and Product Navigation have distinct responsibilities and must remain separate.
3. Level 1 represents the first supported global hierarchy.
4. Level 2 must belong to a documented parent group.
5. Level 3 or deeper hierarchy is not currently approved.
6. `Expanded` communicates visible hierarchy; `Active` communicates current destination. They are independent concepts.
7. A parent group must not use the same interaction target for both expansion and destination navigation.
8. If a parent context also requires a destination page, represent it explicitly as a destination in the hierarchy.
9. When a Level 2 item is Active, that child is the final active destination. Its Level 1 ancestor may preserve contextual/expanded indication but must not duplicate the child's Active treatment.
10. Global destination order is defined by the approved information architecture. User reordering is not part of Core v0.1.
11. Reuse approved Aurora navigation components and states.

## When to Use

Use Global Navigation for persistent, highest-level destinations across the application ecosystem, such as products, modules or major application contexts.

## When Not to Use

Do not use it for:

- product-local destinations;
- tabs;
- breadcrumbs;
- filters;
- progress steps;
- transient actions;
- modal navigation;
- contextual panel navigation.

## Behavior

### Expand / Collapse

Use an explicit control within Global Navigation to toggle `Expanded` and `Collapsed`. Hover must not be the primary mechanism because the interaction must remain predictable for mouse, keyboard and touch contexts.

### Initial State

When no valid preference exists, the first-access state is `Expanded`.

### Preference Persistence

Persist an authenticated user's `Expanded` / `Collapsed` preference between sessions when technically available. If persistent storage is unavailable, preserve the preference for the current session.

### User Control

Users may keep Global Navigation collapsed as a presentation preference. This does not alter the information architecture.

### Navigation Groups

Groups expand and collapse independently. Expanding one group does not automatically collapse another.

### Parent Group Action

Expansion and navigation must use distinct interaction targets when both responsibilities exist.

### Active Hierarchy

The active Level 2 item is the current destination. The Level 1 ancestor preserves contextual indication without duplicating the final destination's Active state.

### Authorization

Authorization determines destination availability. Permission rules remain product/system responsibilities and must not be invented by the Pattern or an AI agent.

By default, destinations the user cannot access should not be presented as available navigation. Product-specific discovery or upsell behavior requires an explicit product decision.

### Ordering

Core Global Navigation ordering is system/product-defined and not configurable by the end user in v0.1.

### Still Undocumented

- routing implementation;
- automatic expansion behavior beyond the explicit control;
- technical permission-resolution logic.

## States

Observed and approved states:

- Default
- Hover
- Focus
- Active
- Disabled
- Group Expanded
- Group Collapsed
- Navigation Expanded
- Navigation Collapsed

## Responsive Behavior

- **Desktop:** observed and supported by product evidence.
- **Tablet:** not yet validated.
- **Mobile:** generic Aurora navigation components include mobile variants, but Global Navigation product behavior is not yet validated.
- **Reduced viewport overlay/drawer:** not defined.
- **Numeric breakpoints:** not defined.

Do not interpret the observed 380 px and 56 px component widths as responsive breakpoints.

## Accessibility

Current requirements:

- all destinations and controls must be operable without a mouse;
- interactive controls must expose visible focus;
- Tab order must follow a logical navigation sequence;
- activation must follow the semantic behavior of the native control used;
- the navigation must not create keyboard traps;
- expandable controls must expose their expanded/collapsed state semantically;
- the current destination must expose its state semantically;
- every interactive element requires an accessible name.

Still requiring Accessibility/Engineering specification:

- exact arrow-key model;
- exact ARIA roles and attributes;
- focus restoration behavior;
- landmark semantics.

These implementation details must not be invented by an AI agent before validation.

## Content Guidelines

Use labels that represent global destinations, products, modules or major application contexts and match the approved information architecture.

Do not place transient actions such as `Export`, `Save`, `Add` or `Apply filter` among global destinations.

## Do

- keep Global Navigation inside Application Shell;
- separate global and product-local navigation;
- use an explicit expand/collapse control;
- start Expanded on first access when no preference exists;
- preserve the user's navigation presentation preference when possible;
- allow Navigation Groups to expand independently;
- preserve Level 1 → Level 2 hierarchy;
- preserve visible focus and keyboard operability;
- use approved Aurora navigation structures.

## Don't

- recreate Global Navigation inside individual features;
- mix Product Navigation destinations with global destinations;
- create Level 3 or deeper hierarchy without evidence and approval;
- use hover as the sole expansion mechanism;
- treat `Expanded` as equivalent to `Active`;
- make a single control both navigate and expand a group;
- use Global Navigation as an action menu;
- invent tablet, mobile, drawer or overlay behavior;
- invent routing or business permission rules;
- make Core global ordering user-configurable;
- invent exact ARIA implementation before Accessibility/Engineering validation.

## Product Examples

### ERP — `19471:1938`

```text
Application Shell
├── Header/Hero
├── Global Navigation
└── ERP Workspace
    └── Product Navigation
```

This example is important because it shows the global and product navigation levels simultaneously.

### Notifications Open — `19278:327`

```text
Application Shell
├── Header/Hero
├── Global Navigation
├── Workspace
└── Notification Panel overlay
```

This confirms that contextual overlays can coexist with Global Navigation without replacing it.

## AI Guidance

### Must

- place Global Navigation inside Application Shell;
- keep it separate from Product Navigation;
- reuse Aurora Navigation/Global, Navigation/Group and Navigation/Item structures when available;
- preserve Level 1 → Level 2 as the deepest currently approved hierarchy;
- use an explicit expand/collapse control;
- use Expanded as the first-access state unless a valid user preference exists;
- preserve the user's Expanded/Collapsed preference when implementation supports persistence;
- keep group expansion independent;
- keep Active and Expanded semantically distinct;
- maintain keyboard operability and visible focus.

### Should

- prefer the shallowest supported hierarchy;
- maintain stable global destinations across screens of the same application ecosystem;
- use product information architecture to define ordering;
- hide unavailable destinations when authorization says the user cannot access them, unless product requirements explicitly define another treatment.

### Must Not

- recreate Global Navigation inside a feature;
- mix product-local destinations with global destinations;
- invent Level 3 or deeper hierarchy;
- invent tablet, mobile, drawer or overlay behavior;
- treat 380 px or 56 px as breakpoints;
- invent routing or business permission rules;
- use hover as the sole expansion mechanism;
- make Core ordering user-configurable;
- invent exact ARIA implementation details before validation.

## Known Limitations

The current contract is strong for desktop structure, hierarchy, states and separation of responsibilities. Responsive product behavior and the complete technical accessibility model remain incomplete.

## Open Questions

1. What exact ARIA roles, attributes and focus-restoration behavior will be standardized with Accessibility/Engineering?
2. What is the validated Global Navigation behavior on tablet?
3. What is the validated Global Navigation behavior on mobile?
4. Should reduced viewports use an overlay, drawer or another navigation presentation after responsive validation?

## Related Patterns

- `application-shell`
- `product-navigation`
- `breadcrumb-navigation`
- `tabbed-workspace`

## Version History

### 0.1.0 — Draft

Initial Global Navigation Pattern Contract, including DIF-guided decisions for expansion, persistence, hierarchy, authorization boundaries, ordering and accessibility requirements.
