# Review and score

Run this at the end of every screen. Be strict: you are the senior designer reviewing a junior's work, not the author defending it.

## Step 1: tells check

Go through the "Tells that scream AI made this" list in `SKILL.md`. Any tell present is fixed before scoring. Do not score a screen that still has one.

## Step 2: score

Score each row 0, 1 or 2.

| # | Check | 0 | 1 | 2 |
| --- | --- | --- | --- | --- |
| 1 | Job and primary action | Unclear what the screen is for | Clear job, but two actions compete | One job, one obvious primary action |
| 2 | Hierarchy (squint test) | Everything looks equally important | Main thing visible, groups unclear | Main thing, groups and action all clear when blurred |
| 3 | Spacing | Random values | Mostly on scale, a few one-offs | Every value from the scale; groups separated by space |
| 4 | Typography | More than 6 sizes or mixed families | Scale used, hierarchy relies on size alone | Tight scale; hierarchy through color and weight first |
| 5 | Color discipline | Several accents or decorative color | One accent, used too often | Neutrals dominate; accent marks only what matters |
| 6 | Alignment | Elements align to nothing | Mostly aligned, a few strays | One grid, shared edges everywhere |
| 7 | Real content | Lorem ipsum or obviously fake data | Realistic but too uniform | Realistic, varied, includes edge cases |
| 8 | States | Only the happy path | Some states | Empty, loading, error and long content covered |
| 9 | Accessibility | Fails contrast or tiny targets | Passes contrast, misses focus or labels | Contrast, targets, focus, labels and text scaling all pass |
| 10 | Platform fit | Ignores platform conventions | Mostly native, a few web-isms | Feels like it belongs on its platform |

**Total out of 20. Ship at 16 or higher.** Below 16, fix the lowest rows first and score again.

## Step 3: report

Tell the user:

- The score, with any row below 2 and why.
- What you changed during review.
- Anything you could not fix and what you would need (real content, brand colors, an icon set).

## Quick fixes by symptom

| Looks... | Usually because | Fix |
| --- | --- | --- |
| Cluttered | Too many containers and colors | Remove cards, borders and tints; group with space |
| Flat, boring | No contrast between levels | Make the one key element bigger or heavier; quiet everything else |
| Cheap | Default shadows, radii and gradients | Swap to tokens: border instead of shadow, one radius scale, no gradient |
| Amateur | Misalignment and inconsistent spacing | Snap everything to the grid and spacing scale |
| Generic, "AI" | Default palette, emoji, icon-card grids | Real content, one accent, real screenshots, platform components |
| Hard to read | Low contrast, long lines, small text | Darker text, max 65ch, 16px body |
