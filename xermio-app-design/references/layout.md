# Layout

Layout is the order in which things are understood. On a phone you have about one screen to make the point. Space is the main tool; boxes are the backup.

## Above the fold

- Design for a 6.1-inch phone first (about 393 x 852pt). Write down what is visible before any scrolling.
- The thing the user came for is in that first view, near the top, in the largest type.
- Large titles sit directly above their content. An empty band between the status bar and the first content is the most common layout bug in generated apps.
- A hero element is earned, not default. If one card takes more than about 40 percent of the first view on a screen opened daily, it is crowding out the content people came for.

## Density follows frequency

| How often the screen is opened | Density | Example |
| --- | --- | --- |
| Many times a day | High: more items, smaller chrome, no explanations | Inbox, music home, banking home, task list |
| Daily or weekly | Medium | Fitness summary, shopping home |
| Rarely or once | Low: one idea, room to explain | Onboarding, paywall, empty states, settings detail |

## Thumb reach

- On phones, the primary action lives in the lower half: a bottom bar, a button above the home indicator, or a floating button on Android.
- Destructive and rare actions go up and away (top bar menus).
- Avoid primary actions in the top corners on large phones.

## Grids and edges

- Phones: 16pt side margins (20pt on larger iPhones), every element aligned to them.
- Every element shares an edge with something: a margin, a baseline, a column. Things that align to nothing look accidental.
- Optical alignment beats geometric alignment: nudge play triangles, chevrons and icons next to text by 1 to 2pt until they look centered.
- Tablets: list and detail side by side, not a stretched phone layout.

## Spacing that groups

- Proximity: things that belong together sit closer than things that do not.
- Space between groups is at least twice the space within a group.
- Inside an app view, 24 to 32pt between sections; 8 to 12pt between related items; 16pt padding in containers.
- Consistent padding inside every container of the same type.

## Floating layers

- Tab bars, mini players, floating buttons, toolbars and the keyboard sit on top of content. The content must be inset so its last item and every section title stay visible when scrolled to the end.
- Never stack more than two floating layers at the bottom (for example tab bar plus mini player).

## The squint test

Blur the screenshot. You should see one most important thing, two or three groups, and the primary action. If everything blurs into the same texture, there is no hierarchy.

## Lists

- Row height 44 to 56pt on touch.
- Fixed leading column for icons or images; one primary line, one quiet secondary line; one trailing element.
- Horizontal dividers only, inset to the text; no vertical lines; no cards per row.

## Forms

- Labels above or inside native grouped rows, always visible. Placeholder is an example, never the label.
- One column. Two short fields side by side only when they are one concept.
- Inputs at least 44pt tall on touch.
- Primary button at the bottom, in thumb reach, labeled with the outcome ("Create account").
- Errors next to the field, in plain words.

## Dashboards (web and tablet)

- Answer the question the user opens it with first, top left, biggest.
- Three or four key numbers, each with a comparison in muted text.
- One chart that answers the main question beats six small ones. Many dashboards are best as a table with a header.
