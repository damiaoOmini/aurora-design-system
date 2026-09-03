# Alert

Aurora Alert communicates inline or full-width feedback with explicit semantic intent.

## Source
- Figma: `Alert`
- Node: `1130:81134`
- 24 variants

## Axes
- Color: Brand, Gray, Default, Error, Warning, Success
- Size: Floating, Full-width
- Breakpoint: Desktop, Mobile

All 6 × 2 × 2 combinations exist.

## Properties
- Close button visibility
- Actions visibility
- Supporting text visibility

## Composition
Alert reuses Aurora Buttons, close controls and intent icons rather than redefining those contracts.

## AI rules
1. Preserve the six semantic Color values.
2. Use only Floating and Full-width sizes.
3. Treat Desktop/Mobile as named variants, not numeric breakpoints.
4. Reuse Button and icon contracts.
5. Do not infer auto-dismiss timing, persistence, stacking, announcement priority or ARIA live-region behavior.

## Status
Initial Aurora Alert contract extracted from Figma.