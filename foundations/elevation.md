# Elevation

Aurora elevation defines the approved shadow scale used to communicate depth and separation between interface surfaces.

## Source of truth

The current elevation scale was extracted from the approved Aurora Figma library using its local Effect Styles.

Machine-readable source:

- `tokens/elevation.json` — 8 elevation styles

The Figma file currently contains 26 Effect Styles in total. Not all effects are elevation levels, so Aurora keeps elevation separate from focus rings, backdrop blurs, portfolio mockup effects and avatar-specific effects.

## Elevation scale

The core elevation styles are:

- `shadow-xs`
- `shadow-xs-skeuomorphic`
- `shadow-sm`
- `shadow-md`
- `shadow-lg`
- `shadow-xl`
- `shadow-2xl`
- `shadow-3xl`

Each token may contain one or more shadow layers. Consumers must apply the complete array of layers rather than selecting only one layer from a multi-layer token.

## Structure

Each shadow layer in `tokens/elevation.json` records:

- effect type: drop shadow or inner shadow;
- horizontal offset (`x`);
- vertical offset (`y`);
- blur radius;
- spread;
- color including alpha.

Example:

```json
"shadow-md": [
  { "type": "drop-shadow", "x": 0, "y": 2, "blur": 4, "spread": -2, "color": "#0000000F" },
  { "type": "drop-shadow", "x": 0, "y": 4, "blur": 6, "spread": -1, "color": "#0000001A" }
]
```

## Skeuomorphic variant

`shadow-xs-skeuomorphic` is not merely a stronger `shadow-xs`. It combines the base drop shadow with inner shadows and must be treated as a specific approved effect.

Agents must not recreate it by visually approximating the effect.

## Related effects that are not elevation levels

The Figma Effect Styles also contain:

- 7 focus-ring styles;
- 4 backdrop-blur styles;
- 5 portfolio-mockup shadow styles;
- 2 avatar-specific effects.

These effects are valid Aurora assets, but they are not part of the general elevation scale documented here.

Focus rings communicate interaction and accessibility state, not depth. Backdrop blur controls surface transparency/blur behavior. Portfolio and avatar effects are specialized assets and must not be promoted to global elevation levels without an explicit Design System decision.

## Usage rules

- Use an approved elevation token instead of manually composing a shadow.
- Preserve every layer of a multi-layer shadow.
- Do not interpolate new levels between existing tokens.
- Do not use a focus ring as an elevation shadow.
- Do not use portfolio or avatar-specific effects as generic product elevation.
- Do not infer component-to-shadow mappings until those rules are documented at component or pattern level.
- A visually similar CSS shadow is not equivalent if its offsets, blur, spread or alpha differ from the approved token.

## Guidance for AI agents

When generating an Aurora interface, an AI agent should:

1. Determine whether the requested effect represents actual surface elevation.
2. If yes, select one of the approved tokens in `tokens/elevation.json`.
3. Apply all layers in the order stored in the token.
4. Preserve offset, blur, spread and color values exactly.
5. If the design requires focus indication, blur, portfolio styling or avatar treatment, do not substitute an elevation token; treat that as a separate effect category.

AI agents must not invent a new shadow because a requested depth is not represented in the current scale. That absence should be treated as a missing Design System decision.

## Status

Elevation foundation extraction is complete for the current Aurora source:

- Core shadow scale: extracted
- Multi-layer shadows: preserved
- Skeuomorphic shadow: preserved
- Related non-elevation effects: identified and separated
- AI consumption rules: documented

Future changes to the elevation scale should update `tokens/elevation.json` and this documentation together.