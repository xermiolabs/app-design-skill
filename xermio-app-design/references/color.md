# Color

Most good interfaces are almost colorless. Color is a signal, so it only works when it is rare.

## The 80 / 15 / 5 rule

- About 80 percent: background and surfaces (white, near-white, or a dark base).
- About 15 percent: text, borders, icons in neutral tones.
- About 5 percent: the accent, on the primary action, the active state and the one number that matters.

If a screen has the accent in more than three places, remove some.

## Building a palette

1. Pick a neutral family, warm or cool (see `tokens.md`). Match it to the accent: cool neutrals for blue, green, teal; warm for orange, coral, olive, gold.
2. Pick one accent. Check it against white at 4.5:1 if it will carry text (button labels on it are white, so check white on the accent too).
3. Semantic colors (success, warning, danger) should be muted versions that sit beside the accent without fighting it. Use them only for meaning, never decoration.
4. Write every color as a token. No hex values inline in components.

## Text and background pairs

| Pair | Minimum | Notes |
| --- | --- | --- |
| Body text on background | 4.5:1 | Includes secondary text people must read |
| Large text (24px+, or 19px+ bold) | 3:1 | |
| Icons, borders of inputs, focus rings | 3:1 | Against the adjacent color |
| Placeholder text | Treat as body if it carries meaning | Better: use a real label |
| Disabled controls | No requirement | But they must still look disabled, not invisible |

Use near-black instead of pure black for text on white (for example `#14171C`). Pure `#000` on pure `#FFF` vibrates on screens and looks harsh.

## Dark mode

Dark mode is a second palette, not an inverted one.

- Base background around `#0B0D10` to `#121212`, not pure black (pure black is fine for OLED-first media apps).
- Show elevation with lighter surfaces: base, then +4 to +8 percent lightness for cards, more for popovers. Shadows barely show on dark backgrounds.
- Text: primary around `#EDEEF0`, not pure white; secondary around 65 to 70 percent.
- Desaturate and lighten the accent slightly so it does not glow.
- Borders get lighter (for example `rgb(255 255 255 / 0.08)`), not darker.
- Re-check every contrast pair. Colors that pass on light often fail on dark.
- On iOS and Android, semantic system colors (`label`, `systemBackground`, Material color roles) handle most of this for you. Use them.

## Gradients

- Only when the brand has one. Then use it once (a hero, a single illustration), never on buttons, text and backgrounds at the same time.
- The purple-to-blue gradient is the single strongest "AI made this" signal. Do not use it by default.
- A subtle neutral gradient (white to off-white) on a large surface is fine and often invisible. That is the point.

## Charts and data

- Start grey, add color for what the user should look at.
- Categorical data: up to 5 or 6 distinct hues, then group the rest as "Other".
- Sequential data (low to high): one hue in steps of lightness.
- Good vs bad: green and red, muted, and never color alone (add an arrow, sign or label for color-blind users).

## Quick fixes for a muddy screen

- Remove every tinted background that does not group something. Go back to white or one surface color.
- Replace colored icons with neutral ones; keep color only on the active one.
- Turn secondary buttons into neutral outline or text buttons.
- Check that the accent appears in one obvious place first.
