# Layout

Aurora layout defines approved width scales, container constraints and grid structures for product interfaces.

## Source of truth

The current layout foundation was extracted from the approved Aurora Figma library.

Figma sources:

- `4. Widths` — reusable width scale
- `5. Containers` — container paddings and desktop max width
- Local Grid Styles — desktop, tablet, mobile and auxiliary column grids

Machine-readable source:

- `tokens/layout.json`

## Width scale

Aurora provides reusable widths from 320px to 1920px, plus a paragraph maximum width.

| Token | Value |
| --- | ---: |
| `width-xxs` | 320px |
| `width-xs` | 384px |
| `width-sm` | 480px |
| `width-md` | 560px |
| `width-lg` | 640px |
| `width-xl` | 768px |
| `width-2xl` | 1024px |
| `width-3xl` | 1280px |
| `width-4xl` | 1440px |
| `width-5xl` | 1600px |
| `width-6xl` | 1920px |
| `paragraph-max-width` | 720px |

The machine-readable source also preserves each primitive spacing alias used by Figma.

## Containers

Approved container values:

- `container-padding-mobile` → 16px
- `container-padding-desktop` → 32px
- `container-max-width-desktop` → 1280px

These values describe container constraints. They do not by themselves define viewport breakpoints.

## Primary grids

### Desktop

- 12 stretch columns
- 32px gutter
- 112px outer offset in the approved Figma grid style

### Tablet

- 6 stretch columns
- 32px gutter
- 32px outer offset

### Mobile

- 4 stretch columns
- 16px gutter
- 16px outer offset

The Figma grid styles also contain supporting row and centered boundary grids. The primary column definitions above are the core structure used for machine-readable layout guidance.

## Auxiliary grids

Aurora also contains reusable automatic column grid styles:

- 12 columns / 32px gutter
- 6 columns / 32px gutter
- 5 columns / 32px gutter
- 3 columns / 32px gutter
- 2 columns / 32px gutter

These are reusable grid configurations, not separate responsive breakpoints.

## Breakpoints

Explicit viewport breakpoint thresholds were not found in the extracted collections or Grid Styles.

The names `desktop`, `tablet` and `mobile` identify approved layout configurations, but they do not provide enough evidence to define values such as `768px`, `1024px` or other media-query thresholds.

Until explicit breakpoint rules are documented, Aurora consumers must not invent them and present them as Design System decisions.

## Usage rules

- Use the approved container padding rather than arbitrary page-edge spacing when the container model applies.
- Respect `container-max-width-desktop` when implementing a constrained desktop container.
- Use `paragraph-max-width` for text measure only when the product pattern calls for constrained long-form content.
- Use the named grid configuration that matches the documented product context instead of creating an ad hoc column system.
- Do not interpret every width token as a breakpoint.
- Do not treat auxiliary grids as responsive states by default.
- Component-specific widths and layouts should be documented with the component or pattern rather than inferred from this Foundation alone.

## Guidance for AI agents

When an AI agent creates or modifies an Aurora interface:

1. Read `tokens/layout.json` before selecting structural dimensions.
2. Use semantic container values when building page-level containers.
3. Use the approved desktop, tablet or mobile grid configuration when that context is explicitly known.
4. Preserve the documented column count and gutter for the selected grid.
5. Use width tokens for constrained regions rather than introducing visually similar arbitrary values.
6. Treat missing breakpoint thresholds as an unresolved Design System decision.

AI agents must not:

- invent breakpoint thresholds and attribute them to Aurora;
- create a new width scale because a desired size falls between existing tokens;
- assume that `width-xl = 768px` is automatically a tablet breakpoint;
- replace the approved 16px or 32px container paddings with arbitrary values;
- infer component layouts solely from the page grid.

## Status

Layout foundation extraction is complete for the current machine-readable scope:

- Width scale: extracted
- Container values: extracted
- Desktop grid: extracted
- Tablet grid: extracted
- Mobile grid: extracted
- Auxiliary column grids: extracted
- Explicit breakpoint thresholds: not defined in the extracted Aurora source

Future breakpoint decisions should be added only when they become an approved Aurora rule.