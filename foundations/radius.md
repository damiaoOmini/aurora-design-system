# Radius

Aurora radius defines the approved corner-radius scale used by components, containers and surfaces.

## Source of truth

The current radius scale was extracted from the approved Aurora Figma library.

Figma collection:

- `2. Radius` — radius scale

Machine-readable source:

- `tokens/radius.json` — 11 radius tokens

The Figma collection stores direct numeric values. There are no aliases in this collection.

## Scale

| Token | Value |
| --- | ---: |
| `radius-none` | 0px |
| `radius-xxs` | 2px |
| `radius-xs` | 4px |
| `radius-sm` | 6px |
| `radius-md` | 8px |
| `radius-lg` | 10px |
| `radius-xl` | 12px |
| `radius-2xl` | 16px |
| `radius-3xl` | 20px |
| `radius-4xl` | 24px |
| `radius-full` | 9999px |

## Usage rules

- Use the named Aurora radius tokens instead of arbitrary corner-radius values.
- `radius-none` removes rounding.
- `radius-full` is the approved maximum-radius token and should be used where a fully rounded shape is required.
- The existence of a value in the scale does not define which component should use it; component-specific decisions belong in component documentation.
- Do not introduce intermediate radius values unless they become an approved Aurora design decision.
- Consumers should reference the token name rather than duplicating its numeric value as a new Design System rule.

## Guidance for AI agents

When an AI agent creates or modifies an Aurora interface:

1. Check the component or pattern documentation for a defined radius token.
2. If a radius token is specified, use that exact token.
3. If only the radius foundation applies, select from `tokens/radius.json`; do not invent a new value.
4. Treat `radius-full` as the system token for fully rounded shapes rather than replacing it with another arbitrary large number.
5. Do not infer component-specific radius assignments from visual similarity alone.

If a component requires a radius rule that is not documented, treat it as a missing Design System decision rather than silently defining a new one.

## Status

Radius foundation extraction is complete for the current Aurora source:

- 11 radius tokens extracted
- Direct Figma values preserved
- Machine-readable source created
- AI consumption rules documented

Future changes to Aurora radius values should update `tokens/radius.json` and this documentation together.