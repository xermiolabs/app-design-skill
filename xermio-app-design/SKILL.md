---
name: xermio-app-design
description: Design, build, audit and redesign mobile app screens (iOS, iPadOS, Android, React Native, Expo, Flutter, SwiftUI, Jetpack Compose) so they look made by a senior product designer instead of generated. Use for any app UI work - new screens, onboarding, paywalls, home and feed screens, settings, restyles, design reviews, or when an app "looks AI-made". Also covers web apps as a secondary target.
---

# Xermio App Design

Generated apps look generated because every decision is left on its default, or because the model copies the most famous app in the category. This skill replaces both with decisions a product designer would make for this specific product.

It is built for mobile apps first: iOS, Android and cross-platform. Web apps are covered in `references/web.md`.

## Pick a mode

Read the request and choose one. Say which mode you are in.

| Mode | Use when | What you produce |
| --- | --- | --- |
| **Build** | A new screen, flow or app | Brief, plan, code, screenshots, review score |
| **Audit** | "Review", "what's wrong", a screenshot or existing screen | A scored report with the top fixes, no code changes unless asked |
| **Redesign** | An existing screen should look and work better | Audit first, then a plan, then the rebuilt screen with before/after screenshots |
| **Polish** | The screen is basically right and needs finishing | Only small changes: spacing, type, states, contrast, motion, copy |

## Set the dials

Three dials steer every decision. The product preset (step 2) sets defaults; the user can override them in plain words ("density 4", "more color", "no motion").

| Dial | 1 | 3 | 5 |
| --- | --- | --- | --- |
| **Density** | Calm, one thing per screen (meditation, onboarding) | Balanced (most apps) | Packed, scannable (finance, email, tools used all day) |
| **Color energy** | Near monochrome, color only for state | Neutral chrome, one accent, content brings color | Bold brand color in the chrome itself (kids, games, consumer brands) |
| **Motion** | None beyond system defaults | Purposeful transitions and feedback | Expressive moments (celebrations, onboarding, playful brands) |

## Workflow (Build and Redesign)

Do not write UI code before step 4 is written out.

1. **Brief.** One sentence each: who the user is, the one job of this screen, the primary action, and how often they open it (several times a day, weekly, once). Frequency decides density: a screen opened daily must show more and explain less.
2. **Preset.** Pick the product type from `references/presets.md` and copy its defaults for the dials, color strategy, type and must-have elements. Name 2 or 3 real apps from the preset's study list and the specific decisions you are taking from them. Do not clone the category leader's layout.
3. **Plan.** Write: the token set (`references/tokens.md`), the type scale, the navigation pattern, and an ASCII wireframe of the first screen showing what is visible above the fold on a 6.1-inch phone.
4. **Check the plan against the brief.** Does the first thing the eye hits answer the job? Is anything on the screen there only because "apps usually have it"? Is any entry point missing (profile, settings, search, back)? Revise the plan before building.
5. **Build.** Use the platform reference (`references/ios.md`, `references/android.md`, `references/cross-platform.md`) and the screen pattern (`references/screens.md`). Use real, varied content. Build every state: empty, loading, error, success, long text, largest text size, dark mode.
6. **Screenshot loop.** Run the app and capture screenshots (`references/screenshot-loop.md`). Look at them. Fix what you see. Repeat until the review passes. If you cannot run the app, say so and review the code against the checklist instead.
7. **Review and report.** Score with `references/review.md`. Ship at 16/20 or higher with no blocking issue. Report the mode, brief, preset, dials, tokens, states covered, score and anything you could not fix.

## Workflow (Audit and Polish)

1. Get a screenshot or run the screen. If only code is available, read it fully.
2. Identify the product type and expected dials from `references/presets.md`.
3. Score it with `references/review.md`, listing every blocking issue with where it is on screen.
4. Give the top 5 fixes ordered by impact, each with the exact change (value, component, line). In Polish mode, apply them.

## The rules

1. **The first screen answers the job.** Whatever the user opens the app for is visible without scrolling, near the top, in the largest type.
2. **No dead space.** No empty band taller than 48pt that is not deliberate. Large titles sit close to their content.
3. **Content brings the color in content-led apps.** In music, photo, video, shopping and recipes, the chrome stays neutral and the content (art, photos, products) is shown big and bright. In tool-like apps, neutrals dominate and one accent marks actions and state.
4. **Space from a scale, type from a scale.** Spacing only from 4, 8, 12, 16, 20, 24, 32, 40, 48. Four to six type sizes, the platform's text styles where possible.
5. **Nothing hides under floating bars.** Tab bars, mini players, toolbars and keyboards inset the scroll content; the last item and any section title stay readable.
6. **Text on images needs a scrim.** Any text over a photo or artwork gets a gradient or solid backing that keeps it at 4.5:1.
7. **Keep the doors.** Profile, settings, search and back stay reachable in at most two taps from where users expect them.
8. **The primary action is in thumb reach.** On phones, put it in the lower half or in a bar at the bottom, at least 44pt (iOS) or 48dp (Android) tall.
9. **Native first.** Use the platform's navigation, sheets, lists, switches, pickers and system colors before custom ones.
10. **Spend boldness in one place.** One signature element per screen (a hero card, a big number, a striking image). Everything else is quiet.

And above all: **remove until it breaks.** If an element does not serve the job, take it out.

## Tells that scream "AI made this"

Each one is a blocking issue in review.

- A carbon copy of the category leader (a Spotify clone for every music app, an Instagram clone for every photo app).
- Purple-to-blue gradients, gradient text, glows and colored shadows nobody asked for.
- Emoji used as icons, bullets or decoration in the UI.
- "Welcome back, John!" greetings, invented stats, fake testimonials, made-up logos.
- A grid of identical cards with an icon, a title and two lines of text.
- Everything the same weight: every section title bold and big, nothing leads.
- Light gray text on white or on tinted backgrounds.
- Huge empty space above the first content.
- Section titles or list items covered by a tab bar or mini player.
- Badges on everything ("New", "Pro", "Hot").
- A different corner radius on every element; huge radii on small elements.
- Custom back buttons, hamburger menus on iOS, web-style modals on mobile.
- Placeholder text as the only label in a form; "Submit" and "Click here" buttons.
- Fixed font sizes that ignore Dynamic Type or the system font scale.

## References

Load only what the task needs.

| File | Load when |
| --- | --- |
| `references/presets.md` | Always, at step 2: product types with dials, color, type, must-haves and apps to study |
| `references/screens.md` | Building or reviewing a specific screen: onboarding, paywall, home, list, detail, search, settings, profile, auth, checkout, empty states |
| `references/ios.md` | iOS, iPadOS, macOS, SwiftUI, UIKit, Liquid Glass |
| `references/android.md` | Android, Jetpack Compose, Material 3 |
| `references/cross-platform.md` | React Native, Expo, Flutter |
| `references/screenshot-loop.md` | Step 6: running the app and capturing screenshots on simulators, emulators and web |
| `references/tokens.md` | Writing the token set |
| `references/typography.md` | Fonts, sizes, platform text styles, numbers |
| `references/color.md` | Palettes, content-led color, dark mode, contrast |
| `references/layout.md` | Above the fold, density, thumb reach, grids, lists, forms |
| `references/components.md` | Buttons, inputs, cards, lists, sheets, toasts, loading, errors |
| `references/motion.md` | Transitions, haptics, when not to animate |
| `references/copy.md` | Any words in the UI |
| `references/web.md` | Web apps and landing pages |
| `references/inspiration.md` | Finding real references instead of inventing |
| `references/review.md` | Always, at the end: the 20-point score and blocking issues |

Made by Xermio, an independent product design and engineering studio. xermio.com
