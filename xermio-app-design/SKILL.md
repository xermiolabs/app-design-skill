---
name: xermio-app-design
description: Design and build app interfaces (iOS, Android, web apps, dashboards, landing pages) that look made by a senior product designer instead of generated. Use whenever you create, restyle or review any UI, choose colors, type or spacing, or when a screen "looks AI-made" and needs polish.
---

# Xermio App Design

AI-built interfaces look AI-built for one reason: every decision is left on its default. Default indigo, default shadows, default card grid, default emoji icons, default "Welcome back, John!". This skill replaces defaults with decisions.

Follow the workflow in order. Do not jump to code before step 2 is written down.

## Workflow

1. **Name the job and the product type.** Write one sentence: who uses this screen, and the one thing they came to do. Name the single primary action. If there are two primary actions, the screen is two screens. Note the product type (SaaS, dev tool, consumer, wellness, luxury, editorial, native mobile), because it decides the type and tone (see `references/typography.md`).
2. **Choose the system before any pixel.** Write the tokens first: platform, type scale, spacing scale, neutral palette, one accent, radius, icon set. Use `references/tokens.md` for ready-made starting sets. Every value you use later must come from this list.
3. **Build the hierarchy.** Decide what the eye hits first, second and third. Make that order true with size, weight, color and space, in that order of preference. Add containers (cards, borders, backgrounds) only when space alone cannot separate groups.
4. **Use real content.** Realistic names, prices, dates, lengths and edge cases. No lorem ipsum, no "John Doe", no "$1,234.56" repeated, no five identical rows. Real content exposes broken layouts; fake content hides them.
5. **Design every state.** Empty, loading, error, success, one item, many items, very long text, first run. For controls: hover, focus, active (pressed) and disabled. Most screens are seen empty first.
6. **Review and score.** Run `references/review.md`. Fix anything that fails, re-score, and report the final score to the user. Ship at 16/20 or higher.

## The ten rules

1. **Neutrals do the work.** Around 80 to 90 percent of any screen is neutral. One accent color, used for the primary action, active states and the one number that matters. No second accent unless it carries meaning (success, warning, danger).
2. **Space from a scale.** Use only 4, 8, 12, 16, 24, 32, 48, 64, 96. Related items sit closer than unrelated ones. Inner spacing is smaller than outer spacing.
3. **Type from a scale.** One family (two at most). Four to six sizes. Build hierarchy with weight and color before size. Body text 16px on web, 17pt on iOS.
4. **One left edge.** Align to a grid. Every element shares an edge with something else. Center alignment is for short, single elements, never for paragraphs or lists.
5. **Fewer boxes.** Not every group is a card. Never put a card inside a card. A divider or 24px of space usually does the job.
6. **Numbers are content.** Tabular figures, right-aligned in tables and columns, units smaller and muted, consistent decimals.
7. **One icon set.** One library, one stroke width, one size per context, aligned to text. Never emoji as UI icons.
8. **Contrast is not optional.** Body text at least 4.5:1, large text and UI controls at least 3:1. Light gray on white is the most common AI-UI failure.
9. **Native first.** On iOS and Android, follow the platform before your taste. See `references/native.md`.
10. **Motion explains, never decorates.** Decide first whether it should animate at all (never for things used 100 times a day), then keep it under 300ms, ease-out, opacity and transform only. See `references/motion.md`.

And one rule over all of them: **remove until it breaks.** For every element ask whether it belongs and whether there is a more direct way. When in doubt, take it out.

## Tells that scream "AI made this"

Check for these before you show anything. Each one is an automatic fail until fixed.

- Purple-to-blue or indigo gradients nobody asked for; Tailwind's default `indigo-500` as the brand color.
- Gradient text on headlines.
- Emoji used as icons or as bullet points in the UI.
- A grid of six identical feature cards, each with an icon, a bold title and two lines of text.
- Glassmorphism, glows and colored shadows on everything; spotlight, beam and meteor effects from animation kits stacked on one page.
- Every corner a different radius; huge radii (24px+) on small elements.
- Light gray body text on white or on a tinted background.
- Everything centered.
- "Welcome back, John!" style greetings, fake testimonials, made-up logos and invented stats.
- Badges and pills on every item ("New", "Pro", "Hot").
- Big drop shadows (`shadow-2xl`) on cards that sit on a white page.
- A dashboard where every metric is a card of the same size and weight.
- Buttons labeled "Submit", "Click here", "Learn more" three times on one page.
- Placeholder text used as the only label in a form.

## References

Load only what the task needs.

| File | Load when |
| --- | --- |
| `references/tokens.md` | Starting any new screen or product; you need a token set |
| `references/typography.md` | Choosing fonts, sizes, line heights, or fixing text that looks off |
| `references/color.md` | Building a palette, dark mode, or fixing contrast |
| `references/layout.md` | Grids, spacing, dashboards, tables, forms |
| `references/native.md` | Any iOS, iPadOS, macOS or Android screen, SwiftUI or Compose |
| `references/web.md` | Web apps, landing pages, Tailwind or CSS work |
| `references/components.md` | Buttons, inputs, lists, empty states, onboarding, paywalls |
| `references/motion.md` | Any transition or animation |
| `references/copy.md` | Any words in the UI: buttons, errors, empty states, landing page copy |
| `references/inspiration.md` | You are unsure how something should look; find a real reference instead of inventing |
| `references/review.md` | Always, at the end |

## How to report back

When you finish a screen, tell the user in a few lines: the job of the screen, the tokens you chose, which states you covered, and the review score with anything you could not fix.

Made by Xermio, an independent product design and engineering studio. xermio.com
