# Notification

Aurora Notification defines richer transient or contextual feedback compositions distinct from Alert.

## Source
- Figma: `Notification`
- Node: `1135:618`
- 18 variants

## Axes
- Type: Primary icon, Progress indicator, Gray icon, Success icon, No icon, Warning icon, Error icon, Avatar, Image
- Breakpoint: Desktop, Mobile

All 9 × 2 combinations exist.

## Properties
- Close button visibility
- Actions visibility
- Supporting text visibility

## Composition
Notification reuses Aurora Buttons, close controls, Featured Icons, Progress bar, Avatar, Status icon and other icon contracts.

## AI rules
1. Keep Notification distinct from Alert.
2. Use only the nine approved Types.
3. Treat Desktop/Mobile as named variants, not numeric breakpoint thresholds.
4. Reuse nested Aurora contracts rather than recreating them.
5. Do not infer toast placement, delivery channel, auto-dismiss duration, queueing, persistence, announcement priority or ARIA live-region behavior.

## Status
Initial Aurora Notification contract extracted from Figma.