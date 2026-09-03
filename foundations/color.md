# Color

Aurora uses a two-layer color architecture: primitive color values and semantic color roles.

## Source of truth

The current color system was extracted from the approved Aurora Figma library.

Figma collections:

- `_Primitives` — base color values
- `1. Color modes` — semantic color roles with Light and Dark modes

Machine-readable color sources:

- `tokens/colors/primitives.json` — 314 primitive color tokens
- `tokens/colors/semantic.json` — 273 semantic color tokens with Light and Dark mode relationships

These files allow Aurora color decisions to be consumed without requiring Figma as the runtime source.

## Architecture

### 1. Primitives

Primitives are raw color values. They describe the available palette, not where a color should be used.

Examples:

- `Colors/Brand/600` → `#1061A9`
- `Colors/Neutral/900` → `#171717`
- `Colors/Base/white` → `#FFFFFF`

Primitives should remain stable and reusable across semantic roles.

### 2. Semantic colors

Semantic colors describe purpose and usage. They may point to different primitive colors depending on the active mode.

Example:

`Colors/Text/text-primary (900)`

- Light mode → `Colors/Neutral/900` → `#171717`
- Dark mode → `Colors/Neutral/50` → `#FAFAFA`

Semantic colors are stored in `tokens/colors/semantic.json`.

The semantic token source preserves:

- Light and Dark mode values
- aliases to primitive tokens
- aliases between semantic tokens
- direct HEX values where the approved Figma variable uses a direct color instead of an alias
- alpha/transparency values
- the original Aurora token hierarchy

## Reading semantic tokens

In `semantic.json`, each token leaf is represented as an array:

`[light, dark]`

An alias is represented using the referenced Aurora token path inside braces.

Example:

```json
"text-primary (900)": [
  "{Colors/Neutral/900}",
  "{Colors/Neutral/50}"
]
```

A direct value remains a HEX value:

```json
"border-secondary_alt": [
  "#0000001A",
  "{Colors/Neutral/800}"
]
```

Semantic aliases can also reference another semantic token:

```json
"fg-brand-primary_alt": [
  "{Colors/Foreground/fg-brand-primary (600)}",
  "{Colors/Neutral/300}"
]
```

Consumers must resolve these references recursively until reaching a primitive or direct value.

## Usage rules

- Product interfaces should prefer semantic color tokens over raw primitive values.
- Components should not depend directly on a primitive when an appropriate semantic token exists.
- Primitive values must not be changed or invented without an approved Aurora design decision.
- Semantic aliases must preserve their relationship to the primitive layer rather than duplicating resolved HEX values as independent decisions.
- Light and Dark modes are part of the semantic layer, not separate primitive palettes.
- Direct HEX values in `semantic.json` are intentional when they reflect direct values in the approved Figma source.
- Consumers must not replace semantic aliases with arbitrary primitive colors because they appear visually similar.

## Guidance for AI agents

When an AI agent creates or modifies an Aurora interface, it must treat the color files as constraints rather than suggestions.

The expected reading order is:

1. Identify the UI purpose: text, foreground, background, border, effect, utility or component-specific color.
2. Search `tokens/colors/semantic.json` for the semantic token that represents that purpose.
3. Select the value for the active Light or Dark mode.
4. If the value is an alias, resolve the referenced token recursively.
5. Use `tokens/colors/primitives.json` when the alias reaches the primitive layer.
6. Use a direct HEX value only when the semantic token itself explicitly contains that direct value.

AI agents must not:

- invent new Aurora colors;
- choose primitives based only on visual similarity;
- bypass an existing semantic token in favor of a raw HEX value;
- assume the Light value is valid for Dark mode or vice versa;
- flatten semantic relationships when modifying the source token files.

If no appropriate semantic token exists, the agent should treat this as a missing Design System decision rather than silently creating a new color rule.

## Brand

The primary Aurora brand scale is defined in the primitive layer. The current main brand value is:

- `Colors/Brand/600` → `#1061A9`

The Figma primitive collection also contains a `Brand identity/Gestor` group. It is preserved in the extracted token source but should be treated as product/brand-specific until its role in the broader Aurora architecture is formally documented.

## Status

Color foundation extraction is complete for the current Aurora source:

- Primitive colors: extracted
- Semantic colors: extracted
- Light/Dark relationships: preserved
- Semantic aliases: preserved
- AI consumption rules: documented

Future changes to Aurora colors should update the machine-readable token sources and this documentation together.