# Loading Indicator

Loading Indicator defines Aurora's approved visual loading treatments.

## Variants

- 12 variants.
- Style: Line simple, Line spinner, Dot circle.
- Size: sm, md, lg, xl.
- All Style × Size combinations are represented.

## Optional property

Supporting text is exposed as a boolean property and is enabled by default in the source component.

## Observed sizing

The source examples use a 512px composition width with heights of 68px (sm), 84px (md), 100px (lg) and 112px (xl). The 512px width is an observed composition value, not a global Aurora width token.

## Tokens

The component uses Aurora semantic background, foreground and text colors, approved spacing tokens and the text-sm/text-lg typography scale.

## AI usage rules

- Use only Line simple, Line spinner or Dot circle.
- Use the approved sm, md, lg and xl sizes.
- Supporting text may be enabled or disabled according to context.
- Do not infer duration, progress percentage, skeleton behavior, blocking behavior, async lifecycle, timeout, retry logic, announcement semantics or animation implementation from this visual contract. Those decisions belong to Patterns or implementation guidance.