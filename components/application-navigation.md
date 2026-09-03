# Application Navigation

Aurora Application Navigation has two public navigation components: `Sidebar navigation` and `Header navigation`.

## Sidebar navigation
- Node: `1158:90768`
- 17 approved variants

Axes:
- Open: False, True
- Type: Simple, Dual-tier, Slim, Sections dividers, Sections subheadings
- Breakpoint: Desktop, Mobile

The theoretical Cartesian space is 20 combinations, but only 17 are represented. AI must use only approved combinations.

Observed frames include 375×56 and 375×812 mobile compositions and desktop/sidebar widths such as 68, 280, 324 and 536px. These are examples, not breakpoint or global width tokens.

## Header navigation
- Node: `1207:1678`
- 12 approved variants

Axes:
- Type: Simple, Dual-tier, Tabs, Centered
- Mobile open: False, True
- Breakpoint: Desktop, Mobile

Properties:
- Notification counter
- Desktop open

The theoretical Cartesian space is 16 combinations, but only 12 are represented.

Observed frames include 375×56 / 375×812 on mobile and 1440px-wide desktop examples with heights 64, 108 and 128px. These do not define responsive thresholds.

## Internal bases and dependencies
- `_Nav item base`
- `_Nav item dropdown base`
- `_Nav featured card`
- `_Nav menu button`
- `_Nav button`
- `_Nav account card menu item`
- `_Nav account card`
- Badge
- Avatar
- Select
- Dropdown menu
- Button / Button utility
- Background overlay
- Logo / Logomark
- Tab button base
- Aurora icons

## AI rules
1. Keep Sidebar and Header navigation as distinct public components.
2. Do not assume the full Cartesian product of variant axes.
3. Use only combinations represented by the approved Figma sets.
4. Treat Desktop/Mobile as named variants; do not derive numeric breakpoints from example dimensions.
5. Reuse navigation bases and existing Aurora component contracts.
6. Preserve overlay dependency where mobile-open compositions use it.
7. Do not invent routing, permissions, active-item resolution, submenu persistence, focus management, drawer behavior, keyboard navigation or accessibility semantics.

## Status
Initial Aurora Application Navigation contracts extracted from Figma.