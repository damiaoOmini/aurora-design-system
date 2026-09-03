# Typography

Aurora typography defines the approved type families, weights, scale and reusable text-style combinations used across product interfaces.

## Source of truth

The current typography system was extracted from the approved Aurora Figma library.

Figma sources:

- `6. Typography` — 32 typography variables
- Local Text Styles — 44 approved text styles

Machine-readable source:

- `tokens/typography.json`

## Font family

Aurora currently uses `Inter` for both display and body typography.

- Display: `Inter`
- Body: `Inter`

## Font weights

The typography variable collection defines:

- Regular
- Regular italic
- Medium
- Medium italic
- Semibold
- Semibold italic
- Bold
- Bold italic

The 44 extracted local Text Styles use the non-italic variants only: Regular, Medium, Semi Bold and Bold.

Do not infer approved italic Text Styles from the existence of italic weight variables alone.

## Type scale

| Token | Font size | Line height |
| --- | ---: | ---: |
| `text-xs` | 12px | 18px |
| `text-sm` | 14px | 20px |
| `text-md` | 16px | 24px |
| `text-lg` | 18px | 28px |
| `text-xl` | 20px | 30px |
| `display-xs` | 24px | 32px |
| `display-sm` | 30px | 38px |
| `display-md` | 36px | 44px |
| `display-lg` | 48px | 60px |
| `display-xl` | 60px | 72px |
| `display-2xl` | 72px | 90px |

## Text styles

Aurora currently contains 11 size groups with four approved non-italic weights each, for a total of 44 local Text Styles.

Examples:

- `Text sm/Regular`
- `Text sm/Medium`
- `Text sm/Semibold`
- `Text sm/Bold`
- `Display lg/Regular`
- `Display lg/Medium`
- `Display lg/Semibold`
- `Display lg/Bold`

The Text Styles combine family, size, line height, weight and letter spacing into approved reusable typography decisions.

## Letter spacing

The extracted Text Styles establish the following tracking behavior:

- `Display md`, `Display lg`, `Display xl` and `Display 2xl` → `-2%`
- `Display xs`, `Display sm` and all `Text` styles → `0%`

This tracking is part of the approved style combination and should not be removed when reproducing the style outside Figma.

## Usage rules

- Prefer an approved Text Style combination instead of assembling arbitrary font size, weight and line height values.
- Use the typography scale values exactly as defined in `tokens/typography.json`.
- Do not create intermediate font sizes or line heights without an approved Aurora decision.
- Do not assume every defined font weight is approved for every product context.
- Do not infer italic styles merely because italic weight variables exist.
- Preserve the letter-spacing rule attached to each approved style group.
- Component-specific typography decisions should be documented with the component rather than invented from the global scale.

## Guidance for AI agents

When an AI agent generates an Aurora interface, typography should be treated as a constrained system.

The expected reading order is:

1. Identify the role of the text in the interface.
2. Prefer an approved entry from `textStyles` in `tokens/typography.json` when a matching style exists.
3. Preserve its font family, font size, line height, weight and letter spacing as one combination.
4. Use the base `scale` only when a component or pattern explicitly requires composition from typography tokens.
5. If the requested typography role is not documented, treat it as a missing Design System decision rather than creating a new size or style silently.

AI agents must not:

- invent font families;
- introduce arbitrary font sizes or line heights;
- combine scale values into new Text Styles without an approved rule;
- remove negative tracking from large Display styles;
- treat `Semibold` and the Figma font-style label `Semi Bold` as different visual weights;
- assume italic styles are approved local styles when they are not present in the extracted Text Styles.

## Status

Typography foundation extraction is complete for the current Aurora source:

- Typography variables: 32 extracted
- Font families: extracted
- Font weights: extracted
- Font sizes: extracted
- Line heights: extracted
- Local Text Styles: 44 extracted
- Letter spacing: extracted
- AI consumption rules: documented

Future typography changes should update the machine-readable token source and this documentation together.