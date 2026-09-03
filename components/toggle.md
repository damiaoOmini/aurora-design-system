# Toggle

Aurora Toggle defines binary on/off visual controls and optional text composition.

## Source
- Figma: `Toggle`
- Node: `1102:4208`
- 64 approved variants
- Internal base: `_Toggle base`

## Axes
- Type: `Default`, `Slim`
- Pressed: `False`, `True`
- Size: `sm`, `md`
- Text: `False`, `True`
- State: `Default`, `Hover`, `Focus`, `Disabled`

All 64 Cartesian combinations exist.

## Control dimensions
| Size | Default | Slim |
| --- | --- | --- |
| sm | 36×20px | 32×16px |
| md | 44×24px | 40×20px |

Text-bearing examples are 344px wide in Figma. That is an observed composition width, not a global Toggle width token.

## Properties
- Supporting text visibility

## Tokens
Toggle uses semantic brand/primary/tertiary backgrounds, toggle-specific component border tokens, white foreground, secondary/tertiary text, focus ring, approved shadows, `radius-full`, spacing and Aurora text-sm/text-md typography.

## AI rules
1. Preserve `Pressed` independently from interaction `State`.
2. Use only Default/Slim and sm/md.
3. All 64 combinations are approved.
4. Preserve the documented control dimensions.
5. Do not treat 344px as a fixed width.
6. Use Toggle component tokens where present instead of approximating them with generic colors.
7. Do not infer persistence, form behavior, keyboard behavior, ARIA semantics or framework implementation.

## Status
Initial Aurora Toggle contract extracted from Figma.