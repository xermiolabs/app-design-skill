# Typography

Type is most of the interface. Get it right and a plain layout looks designed. Get it wrong and nothing else saves it.

## Families

- One family is enough for almost every app. Two at most: one for UI, one for editorial accents (a serif for headings on a marketing page, a mono for code or IDs).
- Native apps: use the system font (SF Pro on Apple platforms, Roboto or the device font on Android). Custom fonts in native apps are a brand decision, not a default.
- Weights: use two or three (for example 400, 500, 600). Avoid 300 and lighter for anything under 20px.
- Prefer variable fonts and self-hosting. Use OpenType features where they help (`tnum` for numbers, `ss01` style sets, `cv11` alternates in Inter).
- Sentence case for UI labels, buttons and headings ("Create invoice", not "Create Invoice"). Title Case reads as marketing.

## Choose the font for the product, not by habit

Using one font for everything is a default too. Match the type to what the product is.

| Product type | Headlines | Body and UI | Notes |
| --- | --- | --- | --- |
| SaaS, dev tools, dashboards | Geist, Inter | Same family | Pair with Geist Mono for code; Instrument Serif for a quiet editorial accent on marketing pages |
| Technical, data-heavy | IBM Plex Sans, Geist | Same, with tabular numbers | IBM Plex Mono for IDs and logs |
| Friendly consumer, wellness, habits | Plus Jakarta Sans, Nunito Sans, Manrope | Same family | Softer shapes; keep weights moderate |
| Luxury, fashion, beauty, hospitality | Playfair Display, Cormorant Garamond, Bodoni Moda | A clean sans (Inter, Geist) | High-contrast serifs only at 28 to 36px and up, never for buttons or small UI text |
| Editorial, content-heavy | Fraunces, Instrument Serif, Source Serif 4, Newsreader | A strong sans or the serif's text cut | Serif headlines, generous line height for reading |
| Native iOS / Android apps | System font | System font | Custom fonts only as a deliberate brand choice |

Always test at the real size on a real screen. A font that looks elegant at 72px can be unreadable at 13px.

## Web scale

A tight scale that covers most products:

| Token | Size | Line height | Weight | Use |
| --- | --- | --- | --- | --- |
| xs | 12px | 16px | 500 | Labels, metadata, table headers |
| s | 14px | 20px | 400/500 | Secondary text, dense UI, buttons |
| m | 16px | 24px | 400 | Body |
| l | 20px | 28px | 600 | Card and section titles |
| xl | 24px | 32px | 600 | Page titles in apps |
| 2xl | 32px | 38px | 600 | Small hero, big numbers |
| 3xl | 48px | 52px | 600 | Marketing hero |

- Letter spacing: tighten large text (about -0.02em at 32px, -0.03em at 48px and up). Leave body at 0. Small uppercase labels get +0.04em.
- Line length: 45 to 75 characters for reading text (`max-width: 65ch`).
- Use `text-wrap: balance` on headings and `text-wrap: pretty` on paragraphs where supported.

## iOS text styles (default sizes at the standard Dynamic Type setting)

| Style | Size | Weight |
| --- | --- | --- |
| Large Title | 34pt | Regular (often set to Bold in apps) |
| Title 1 | 28pt | Regular |
| Title 2 | 22pt | Regular |
| Title 3 | 20pt | Regular |
| Headline | 17pt | Semibold |
| Body | 17pt | Regular |
| Callout | 16pt | Regular |
| Subheadline | 15pt | Regular |
| Footnote | 13pt | Regular |
| Caption 1 | 12pt | Regular |
| Caption 2 | 11pt | Regular |

Use the styles (`.font(.headline)`), not fixed point sizes, so text scales with the user's setting. Test at the largest accessibility size at least once.

## Hierarchy without shouting

Order of tools, cheapest first:

1. Color: primary vs secondary text color.
2. Weight: 400 vs 600.
3. Size: only when 1 and 2 are not enough.
4. Case and spacing: small uppercase labels for section headers, used sparingly.

A screen with four sizes of bold text has no hierarchy. Pick the one thing that matters and let the rest be quiet.

## Numbers

- Use tabular figures wherever numbers line up or change: `font-variant-numeric: tabular-nums` (CSS), `.monospacedDigit()` (SwiftUI).
- Currency and units: the number carries the weight; the symbol and unit can be smaller or muted.
- Format for humans: 12.4K, 3 min ago, Oct 30. Full precision belongs in a tooltip or detail view.

## Common failures

- Body text at 14px on a marketing page (use 16 to 18).
- Center-aligned paragraphs.
- More than one bold element per line.
- Headings with default letter spacing at 48px+ (they look loose and cheap).
- Gray-on-gray text below 4.5:1 contrast.
- Line height 1.5 on huge headings (use 1.05 to 1.2).
