# Review and score

Run this at the end of every Build, Redesign and Polish, and as the whole job in Audit mode. Review screenshots, not just code. Be the senior designer reviewing someone else's work, not the author defending it.

## Step 1: blocking issues

Any of these stops the screen from shipping, whatever the score. Fix them first.

- [ ] Any item from the "Tells that scream AI made this" list in `SKILL.md`.
- [ ] The job of the screen is not answered above the fold.
- [ ] An empty band taller than 48pt that is not deliberate (most often under the status bar or a large title).
- [ ] Content, a section title or the last list item hidden under a tab bar, mini player, toolbar, notch or keyboard.
- [ ] Text on an image without a scrim, or any text below 4.5:1 contrast (3:1 for large text).
- [ ] Tap targets smaller than 44pt (iOS) or 48dp (Android).
- [ ] A missing door: no way to reach profile, settings, search or back where users expect it.
- [ ] Text truncates or overlaps at the largest text size.
- [ ] Broken dark mode (invisible text, unreadable icons, harsh white surfaces).
- [ ] The design is a recognizable copy of the category leader.

## Step 2: score

Score each row 0, 1 or 2.

| # | Check | 0 | 1 | 2 |
| --- | --- | --- | --- | --- |
| 1 | Job and primary action | Unclear what the screen is for | Clear job, but actions compete | One job, one obvious primary action in thumb reach |
| 2 | Above the fold | The answer needs scrolling | Answer visible but small or pushed down | The answer is the first and largest thing |
| 3 | Density fits frequency | Daily screen feels empty, or calm screen feels crowded | Roughly right, some wasted space | Density matches the preset and how often it is opened |
| 4 | Hierarchy (squint test) | Everything looks equally important | Main thing visible, groups unclear | One signature element, clear groups, quiet secondary text |
| 5 | Color | Decorative color, several accents, or muted content in a content-led app | Right strategy, used too often | Matches the preset: content brings color, or one accent marks what matters |
| 6 | Spacing and alignment | Random values, nothing aligns | Mostly on scale, a few strays | Every value from the scale, shared edges everywhere |
| 7 | Typography | Fixed sizes, more than 6 sizes | Platform styles, hierarchy by size alone | Platform styles, hierarchy through weight and color first, scales cleanly |
| 8 | Real content and states | Lorem ipsum, happy path only | Realistic but uniform, some states | Varied real content; empty, loading, error, long text all designed |
| 9 | Accessibility | Fails contrast or targets | Passes contrast, misses labels or text scaling | Contrast, targets, labels, Dynamic Type or font scale, Reduce Motion all handled |
| 10 | Platform fit | Feels like a web page or the other platform | Mostly native, a few foreign patterns | Uses native navigation, controls, sheets and system colors |

**Ship at 16/20 or higher with no blocking issues.** Below that, fix the lowest rows first and score again.

## Step 3: report

In Build, Redesign and Polish:

```
Mode: Redesign
Brief: <one line>
Preset: Content and media (density 4, color 4, motion 3)
Tokens: <short list>
States covered: default, empty, loading, error, dark, largest text
Score: 17/20 (row 3: 1, row 9: 1)
Fixed during review: <list>
Could not fix: <list and what is needed>
Screenshots: <paths>
```

In Audit, list blocking issues first, then the score, then the top 5 fixes by impact. Each fix names the element, where it is, and the exact change ("Move the Play button from the hero card into the bottom bar; height 50pt").

## Quick fixes by symptom

| Looks... | Usually because | Fix |
| --- | --- | --- |
| Empty, flat | Too much space, one giant element, muted content | Remove dead space, show more items above the fold, let content bring color |
| Cluttered | Too many containers, colors and badges | Remove cards, borders, tints and badges; group with space |
| Cheap | Default shadows, radii and gradients | Swap to tokens: one radius scale, no gradient, soft or no shadow |
| Amateur | Misalignment, inconsistent spacing | Snap to the margins and spacing scale |
| Generic, "AI" | Default palette, emoji, icon-card grids, cloned layout | Real content, preset color strategy, platform components, one signature element |
| Foreign | Web or other-platform patterns | Replace with native navigation, controls and sheets |
| Hard to read | Low contrast, small text, text on images | Darker text, larger size, scrims |
