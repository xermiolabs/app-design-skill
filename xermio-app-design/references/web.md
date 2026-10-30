# Web apps and landing pages

## Set the system before writing components

- Define tokens as CSS variables or Tailwind theme values first (see `tokens.md`). Components read tokens; they never hold raw hex values or one-off pixel sizes.
- Load one font family with the two or three weights you use. Self-host or use a fast provider; set `font-display: swap`.
- Set the base: `body { font-size: 16px; line-height: 1.5; color: var(--text); background: var(--bg); -webkit-font-smoothing: antialiased; }`.

## Tailwind without the Tailwind look

The default Tailwind look is: `indigo-600` buttons, `rounded-2xl` everything, `shadow-xl` cards, `gray-500` body text, `bg-gradient-to-r from-purple-500 to-indigo-500` headers. Avoid all of it unless asked.

Use instead:

- Your own color tokens (`bg-accent`, `text-ink`, `text-muted`, `border-line`).
- `rounded-md` or `rounded-lg` consistently; `rounded-full` only for pills and avatars.
- Borders (`border border-line`) instead of shadows on white pages; `shadow-sm` at most for cards.
- `text-muted` that passes 4.5:1. On white, Tailwind's `gray-400` fails (2.5:1), `gray-500` just passes (4.8:1) and can drop below it on gray surfaces, `gray-600` is safe (7.6:1).
- `tracking-tight` on headings 24px and up, `tabular-nums` on numbers, `text-balance` on headings, `max-w-prose` on paragraphs.
- `focus-visible:ring-2 focus-visible:ring-accent/40 focus-visible:ring-offset-2` on every interactive element.

## Hover only where hover exists

Wrap hover styles so touch devices do not get stuck in a hover state after a tap:

```css
@media (hover: hover) and (pointer: fine) {
  .row:hover { background: var(--surface); }
}
```

In Tailwind v4, `hover:` already applies only on devices that support hover.

## Libraries: own the code

Recommended foundation: React, Next.js, TypeScript, Tailwind CSS v4.

| Need | Use | Rule |
| --- | --- | --- |
| Buttons, forms, dialogs, tables, menus | shadcn/ui (ui.shadcn.com) | Copy the code in with the CLI, then change the theme tokens before using anything |
| Animated marketing sections | Magic UI (magicui.design), Aceternity UI (ui.aceternity.com) | One effect per page at most. Effects are the fastest way to look like every other AI-built landing page |
| More blocks and components | 21st.dev and other shadcn-style registries | Treat as a starting point and restyle to your tokens |
| Icons | Lucide (default with shadcn), Phosphor, Heroicons | One set per product |

- Kits are a starting point, not a design. Delete variants you do not need. A product with five button styles has none.
- Keep the same density across components: if inputs are 40px, buttons are 40px.
- When unsure how something should look, study a real product that does it well (Linear, Vercel, Stripe, Apple) or browse `inspiration.md`, instead of inventing.

## Responsive

- Design mobile first, then add columns as width allows. Do not just shrink the desktop layout.
- Breakpoints by content, not devices: switch layout when a line gets too long or a table stops fitting.
- Touch targets 44px on touch devices, even if the desktop version is denser.
- Navigation: 4 to 6 top-level links on desktop; collapse to a clear menu on mobile with large tap rows.

## Landing page skeleton that works

1. Nav: logo, 3 to 5 links, one primary button.
2. Hero: an outcome-first headline (12 words or fewer), one supporting sentence, one primary action, a real product image.
3. Problem: the situation the reader is in, in their words.
4. Solution: benefits, not features, each with a real screenshot. Not a 3 x 3 grid of icon cards.
5. How it works: 3 steps, with a visual each.
6. Proof: real logos, real numbers, or a real quote with a name. Skip the section if there is nothing real.
7. Pricing or offer if relevant: one highlighted plan, the difference between plans in plain words.
8. FAQ: the top real objections.
9. Final call to action, repeating the hero action. Then the footer.

One conversion goal per page, with the same primary call to action repeated two or three times. Copy rules are in `copy.md`.

## Performance is part of design

- Images: modern formats, explicit width and height to avoid layout shift, lazy load below the fold.
- No layout shift when fonts load (`size-adjust` or a matched fallback).
- Skeletons that match the final layout instead of spinners for content areas.
- Animations on `opacity` and `transform` only.

## Accessibility basics that also make it look better

- Semantic elements: `button`, `a`, `nav`, `main`, `label`. A `div` with a click handler is not a button.
- Visible focus states, never `outline: none` without a replacement.
- Alt text that describes purpose. Decorative images get `alt=""`.
- Respect `prefers-reduced-motion` and `prefers-color-scheme`.
