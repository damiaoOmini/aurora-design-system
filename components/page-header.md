# Page Header

Page Header defines the approved top-of-page compositions in Aurora.

## Variants

- 12 variants.
- Style: Simple, Avatar, Banner avatar, Banner avatar centered, Banner simple centered, Banner simple.
- Breakpoint: Desktop, Mobile.
- All Style × Breakpoint combinations are represented.

## Optional properties

- Breadcrumbs
- Supporting text
- Actions
- Search
- Divider

All are exposed as boolean component properties in the source component.

## Composition

Observed dependencies include Breadcrumbs, Button, search Input, Avatar, Badge and icons. Nested Aurora contracts should be reused instead of recreating these elements.

## Layout

The component uses Aurora container tokens including desktop/mobile padding and desktop max width. Observed Figma dimensions are reference compositions and are not global page sizes or numeric breakpoint definitions.

## AI usage rules

- Use one of the six approved styles.
- Treat Desktop and Mobile as named variants only.
- Preserve optional properties only where needed by the page context.
- Reuse Breadcrumbs, Button, Input and other nested Aurora contracts.
- Do not infer page hierarchy, breadcrumb generation, action authorization, search behavior, sticky behavior or breakpoint thresholds from the visual contract.