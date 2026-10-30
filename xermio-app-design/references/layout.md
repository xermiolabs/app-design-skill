# Layout

Layout is the order in which things are understood. Space is the main tool; boxes are the backup.

## Grids and edges

- Web apps: content max width 1200 to 1280px, side gutters `clamp(16px, 4vw, 48px)`. Reading pages: 640 to 720px.
- Phones: 16pt side margins (20pt on larger iPhones is common), content aligned to those margins.
- Every element should share an edge with something: a left edge, a baseline, a center line. Floating elements that align to nothing look accidental.
- Optical alignment beats geometric alignment. A play triangle, a chevron or an icon next to text often looks off-center when it is mathematically centered. Nudge it by 1 to 2px until it looks right.
- One primary column on mobile. Two columns on desktop only when the content has two jobs (list and detail, form and preview).

## Spacing that groups

- Proximity: things that belong together sit closer than things that do not. A label is closer to its field than to the next field.
- Space between groups is at least twice the space within a group.
- Sections on a web page: 64 to 128px apart. Inside an app view: 24 to 32px.
- Consistent padding inside every container of the same type.

## The squint test

Blur your eyes (or blur a screenshot). You should see:

1. The one most important thing.
2. Two or three groups.
3. The primary action.

If everything blurs into the same grey texture, there is no hierarchy. Increase contrast between levels: make the important thing bigger or heavier, and make everything else quieter.

## Dashboards

- Start with the question the user asks when they open it ("Am I on track this month?"). Answer that first, top left, biggest.
- KPI rows: three or four numbers, not eight. Each with a label, the value, and a comparison (vs last period) in muted text.
- Not every metric needs a card. A row of numbers separated by space or thin dividers often reads better.
- One chart that answers the main question beats six small charts nobody reads.
- Tables are fine. Most dashboards are a table with a header.

## Tables

- Text columns left-aligned, number columns right-aligned, header aligned with its column content.
- Row height 40 to 48px (compact: 32 to 36px).
- Horizontal dividers only, light. No vertical lines, no zebra striping by default.
- Hover state on rows, sticky header for long tables.
- Tabular numbers, consistent decimals, units in the header ("Revenue, USD") instead of every cell.
- Truncate long text with an ellipsis and show the full value on hover or in the detail view.

## Forms

- Labels above fields, always visible. Placeholder is an example, never the label.
- One column. Two short fields side by side only when they are one concept (first and last name, city and postcode).
- Inputs at least 40px tall on web, 44pt on touch.
- Group related fields under a small heading with space, not boxes.
- Primary button at the end, aligned with the fields, labeled with the outcome ("Create account", "Save changes").
- Errors appear next to the field, in plain words, with how to fix it.

## Landing pages

- One message per section. One headline per page that says what the product does in plain words.
- The hero shows the real product. A real screenshot or a short loop of it beats any illustration.
- Two calls to action at most in the hero: one primary, one quieter.
- Proof only if it is real: actual customer names, actual numbers. Never invented logos or testimonials.
- Alternate density: a dense section, then a calm one. Not twelve sections of identical cards.
