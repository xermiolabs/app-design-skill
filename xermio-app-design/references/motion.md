# Motion

Motion should explain what happened: where something came from, where it went, what changed. If a movement explains nothing, remove it.

## Step 1: should it animate at all?

Decide by how often people see it.

| How often | Rule | Examples |
| --- | --- | --- |
| Keyboard-driven, or 100+ times a day | Never animate | Command palette opening, list navigation with arrow keys, tab switches in a tool used all day |
| Frequent | Minimal: a fast fade or nothing | Dropdowns, hover states, toggles |
| Occasional | Standard transitions | Modals, sheets, toasts, page changes |
| Rare | Room for a moment of delight | Onboarding, a first success, an upgrade confirmation |

Then check the purpose. Motion earns its place only when it does one of these: keeps spatial continuity (where did this panel come from), gives feedback (my tap registered), shows a state change (saved, loading), or prevents a jarring jump (content reflowing). Anything else is decoration.

## Step 2: timing

| Interaction | Duration |
| --- | --- |
| Button press, hover, color and opacity | 100 to 160ms |
| Tooltips | 125 to 200ms |
| Dropdowns, menus, popovers | 150 to 250ms |
| Modals, sheets, panels | 200 to 300ms (up to 500ms only for large, rare transitions) |

Keep almost everything under 300ms. Exits are shorter than entrances.

## Step 3: easing

- Use ease-out for things entering and leaving: fast start, gentle stop. A strong curve feels crisp: `cubic-bezier(0.23, 1, 0.32, 1)`.
- Avoid ease-in on UI. It starts slow, so the interface feels like it lags behind the tap.
- Never linear for movement (linear is for progress bars and spinners).
- On iOS, prefer springs for gesture-driven motion (`.spring(response: 0.35, dampingFraction: 0.85)` or the system `.smooth`); they feel native and handle interruption.

## Practical rules

- Button press: `transform: scale(0.97)` on `:active`. Small, instant, satisfying.
- Never start from `scale(0)`. Start from `scale(0.95)` with `opacity: 0`.
- Popovers and menus grow from their trigger (set `transform-origin` to the trigger side). Modals stay centered.
- After the first tooltip opens, the next ones skip the delay while the pointer moves between them.
- Prefer CSS transitions over keyframe animations for interactive UI: transitions can be interrupted and reversed mid-way, keyframes cannot.
- Animate only `transform` and `opacity`. Animating width, height, top or left causes jank.
- Stagger list items by 30 to 80ms, and only on first load. Never stagger on every re-render.
- Exit animations: short, with a small `translateY` (4 to 8px) and a fade.
- Modal backdrops: a solid dim (for example `rgb(0 0 0 / 0.4)`) reads better and performs better than a full-screen blur.

## What not to do

- No bounce on every interaction.
- No parallax or scroll-jacking on product pages.
- No looping animation near text people need to read.
- No animated logos in the interface.
- No delay before responding to a tap. Feedback starts on press, not on release.

## Accessibility

- Respect reduced motion: `@media (prefers-reduced-motion: reduce)` on the web, `@Environment(\.accessibilityReduceMotion)` in SwiftUI. Replace movement with a simple fade or no transition.
- Never convey information only through motion.

Credit: the frequency-first framework follows the thinking Emil Kowalski shares at emilkowal.ski.
