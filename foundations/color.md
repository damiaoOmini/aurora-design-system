# Color

Aurora uses a two-layer color architecture: primitive color values and semantic color roles.

## Source of truth

The current color system was extracted from the approved Aurora Figma library.

Figma collections:

- `_Primitives` — base color values
- `1. Color modes` — semantic color roles with Light and Dark modes

Machine-readable primitive values are stored in `tokens/colors/primitives.json`.

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

Semantic color tokens will be stored separately from primitives so their aliases and Light/Dark relationships are preserved.

## Usage rules

- Product interfaces should prefer semantic color tokens over raw primitive values.
- Components should not depend directly on a primitive when an appropriate semantic token exists.
- Primitive values must not be changed or invented without an approved Aurora design decision.
- Semantic aliases must preserve their relationship to the primitive layer rather than duplicating resolved HEX values as independent decisions.
- Light and Dark modes are part of the semantic layer, not separate primitive palettes.

## Brand

The primary Aurora brand scale is defined in the primitive layer. The current main brand value is:

- `Colors/Brand/600` → `#1061A9`

The Figma primitive collection also contains a `Brand identity/Gestor` group. It is preserved in the extracted token source but should be treated as product/brand-specific until its role in the broader Aurora architecture is formally documented.

## Next

The next color step is to extract `1. Color modes` into a machine-readable semantic token file while preserving aliases for Light and Dark modes.
