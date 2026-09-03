# Spacing

Aurora spacing defines the approved distance scale used to organize internal spacing, external spacing, component gaps and larger layout relationships.

## Source of truth

The current spacing scale was extracted from the approved Aurora Figma library.

Figma collection:

- `3. Spacing` — semantic spacing scale

Machine-readable source:

- `tokens/spacing.json` — 17 spacing tokens

The Figma spacing tokens point to primitive spacing variables. The GitHub token source preserves both the original primitive alias and its resolved pixel value.

## Scale

| Token | Primitive alias | Value |
| --- | --- | ---: |
| `spacing-none` | `Spacing/0 (0px)` | 0px |
| `spacing-xxs` | `Spacing/0․5 (2px)` | 2px |
| `spacing-xs` | `Spacing/1 (4px)` | 4px |
| `spacing-sm` | `Spacing/1․5 (6px)` | 6px |
| `spacing-md` | `Spacing/2 (8px)` | 8px |
| `spacing-lg` | `Spacing/3 (12px)` | 12px |
| `spacing-xl` | `Spacing/4 (16px)` | 16px |
| `spacing-2xl` | `Spacing/5 (20px)` | 20px |
| `spacing-3xl` | `Spacing/6 (24px)` | 24px |
| `spacing-4xl` | `Spacing/8 (32px)` | 32px |
| `spacing-5xl` | `Spacing/10 (40px)` | 40px |
| `spacing-6xl` | `Spacing/12 (48px)` | 48px |
| `spacing-7xl` | `Spacing/16 (64px)` | 64px |
| `spacing-8xl` | `Spacing/20 (80px)` | 80px |
| `spacing-9xl` | `Spacing/24 (96px)` | 96px |
| `spacing-10xl` | `Spacing/32 (128px)` | 128px |
| `spacing-11xl` | `Spacing/40 (160px)` | 160px |

## Usage rules

- Use the semantic `spacing-*` scale instead of introducing arbitrary pixel values.
- Component padding, gaps and margins should reference an existing spacing token whenever the approved Aurora component or pattern does so.
- Larger values in the scale can support sections and broad layout separation, but this document does not assign new semantic meaning to individual sizes beyond what is currently established in Aurora.
- Do not infer density variants or responsive behavior from the numeric scale alone.
- Do not create intermediate spacing values simply because they fit a particular screen.
- If a required spacing relationship is not represented by the approved scale or documented component/pattern behavior, treat it as a missing Design System decision.

## Guidance for AI agents

When an AI agent creates or modifies an Aurora interface:

1. Identify the spatial relationship being implemented: padding, gap, margin or layout separation.
2. Check the relevant Aurora component or pattern documentation when available.
3. Use the referenced `spacing-*` token rather than copying a raw pixel value.
4. Read the resolved value from `tokens/spacing.json` when code generation requires pixels.
5. Preserve the token reference in generated specifications or code abstractions whenever the target stack supports design tokens.

AI agents must not:

- invent new spacing values;
- replace a documented spacing token with a visually similar arbitrary number;
- infer component-specific spacing rules from the scale alone;
- assume a spacing value has a specific semantic role unless that role is documented in a component or pattern.

## Status

Spacing foundation extraction is complete for the current `3. Spacing` collection:

- 17 semantic spacing tokens: extracted
- primitive aliases: preserved
- resolved pixel values: preserved
- AI consumption rules: documented

Component-specific and pattern-specific spacing behavior will be documented later in their respective layers.