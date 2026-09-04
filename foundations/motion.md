# Motion

## Status

- **Version:** Aurora v0
- **Status:** Approved
- **Scope:** Core
- **Provenance:** Aurora decisions; values were not extracted from Figma.

## Purpose

Motion communicates the transition between states without becoming necessary to understand the resulting state.

## Approved Tokens

| Token | Value | Use |
|---|---:|---|
| `motion.duration.instant` | `0ms` | Reduced-motion state changes |
| `motion.duration.fast` | `120ms` | Fast internal feedback |
| `motion.duration.structural` | `180ms` | Structural expansion and contraction |
| `motion.delay.enter` | `110ms` | Intent delay before temporary expansion |
| `motion.delay.leaveGrace` | `220ms` | Grace period before temporary collapse |
| `motion.easing.standard` | `cubic-bezier(.2,0,0,1)` | Approved standard transition curve |

## Principles

- Motion must have a functional purpose.
- Motion must not be required to identify or understand state.
- Animate only properties required to communicate the approved transition.
- Do not use `transition: all`.
- Components and patterns consume shared Motion tokens instead of defining arbitrary timings.

## Reduced Motion

When `prefers-reduced-motion: reduce` is active:

- preserve every interaction and final state;
- use `motion.duration.instant`;
- remove spatial animation;
- do not remove functionality or state feedback.

## Navigation/Global Application

- Persistent Expanded participates in layout.
- Persistent Collapsed participates in layout at compact width.
- Temporary Expanded overlays the workspace.
- Pointer entry uses `motion.delay.enter`.
- Pointer exit uses `motion.delay.leaveGrace`.
- Structural expansion and contraction use `motion.duration.structural`.
- Fast internal feedback uses `motion.duration.fast`.
- Transitions use `motion.easing.standard`.
- Keyboard focus provides the same temporary expansion outcome as pointer entry.
- Touch uses explicit control and does not depend on hover.

## Source Boundary

All values in this Motion v0 foundation are approved Aurora decisions. They are not measurements or values extracted from Figma.

## Related Resources

- `tokens/motion.json`
- `patterns/global-navigation.md`
- `patterns/global-navigation.json`

## Version History

### Aurora v0 — Approved

Initial Motion foundation approved for Navigation/Global.
