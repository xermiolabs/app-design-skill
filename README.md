# Xermio App Design Skill

A free skill that makes Claude Code and other coding agents design mobile apps like a senior product designer. Built for iOS, Android, React Native, Expo and Flutter, with web apps as a bonus.

Ask an agent for an app screen and you usually get one of two things: a pile of defaults (purple gradients, emoji icons, identical cards, gray text you can't read) or a copy of the most famous app in the category. This skill gives the agent what a product designer brings instead: a brief, a product-specific preset, platform rules, real screenshots of its own work, and a strict review before anything ships.

Made by [Xermio](https://xermio.com), an independent product design and engineering studio.

## What it does

**Four modes.** Ask in plain words and the agent picks one:

| Mode | Say something like | You get |
| --- | --- | --- |
| Build | "Build the home screen for my budgeting app" | Brief, plan, code, screenshots, review score |
| Audit | "Review this screen" (with a screenshot) | Blocking issues, a score out of 20, the top 5 fixes |
| Redesign | "Redesign this onboarding" | Audit, plan, rebuilt screen, before and after |
| Polish | "Polish this screen" | Small finishing fixes only |

**Three dials.** Density, color energy and motion, each from 1 to 5. Every product preset sets sensible defaults; override them in plain words ("density 4, more color").

**Eleven product presets.** Productivity, content and media, finance, health and fitness, wellness, social, commerce, travel and maps, education and kids, AI assistants, business tools. Each one sets the dials, the color strategy, the must-have elements for the home screen, real apps to study, and the mistakes to avoid. A music app gets its color from album art. A banking app stays calm and dense.

**Screen patterns.** Onboarding, paywall, home and feed, list, detail, search, settings, profile, auth, checkout, and empty, loading, error and offline states.

**Platform rules.** iOS (including Liquid Glass and iOS 26 tab bar accessories), Android (Material 3, edge to edge, insets), React Native, Expo and Flutter, with what to adapt per platform.

**A screenshot loop.** The agent runs your app on the iOS Simulator, Android Emulator or browser, captures light, dark, largest-text and empty states, looks at them, and fixes what it sees.

**A strict review.** Ten blocking checks (content hidden under the tab bar, dead space above the fold, text on images without a scrim, missing profile or back, cloned layouts) and a 20-point score. It ships at 16 or higher with no blocking issues, and tells you the score.

## Install

**One command (Claude Code, Cursor, Codex and other agents that support skills)**

```bash
npx skills add xermiolabs/app-design-skill
```

**Claude Code, by hand**

```bash
git clone https://github.com/xermiolabs/app-design-skill.git
# for every project
cp -r app-design-skill/xermio-app-design ~/.claude/skills/
# or for one project
cp -r app-design-skill/xermio-app-design .claude/skills/
```

**Claude (web and desktop apps)**

Zip the `xermio-app-design` folder and upload it as a custom skill in Claude's settings (Skills must be turned on for your account).

**Other agents**

Put the folder where your agent looks for skills, or paste `SKILL.md` into your project rules and keep the `references` folder next to it.

## Prompts that work well

```
Build the home screen of my iPhone habit tracker in SwiftUI. People open it several times a day.
```

```
Audit this screenshot of my Android app's onboarding. Be strict.
```

```
Redesign the paywall in this Expo app. Content and media preset, density 3.
```

```
Polish the settings screen. Check dark mode and the largest text size.
```

```
Build a recipe app home in React Native for iOS and Android, and adapt it per platform.
```

## What's inside

```
xermio-app-design/
├── SKILL.md                    Modes, dials, workflow, the 10 rules, AI tells
└── references/
    ├── presets.md              11 product types with dials, color, must-haves, apps to study
    ├── screens.md              Onboarding, paywall, home, list, detail, search, settings, auth, checkout, states
    ├── ios.md                  SwiftUI and UIKit, safe areas, Liquid Glass, Dynamic Type, iPad, macOS
    ├── android.md              Jetpack Compose, Material 3, edge to edge, insets, dynamic color
    ├── cross-platform.md       React Native, Expo, Flutter, what to adapt per platform
    ├── screenshot-loop.md      Capturing and reviewing screenshots on simulators, emulators and web
    ├── tokens.md               Spacing, radius, color and type tokens (CSS, Tailwind, SwiftUI)
    ├── typography.md           Fonts by product type, platform text styles, numbers
    ├── color.md                Tool-like vs content-led color, dark mode, contrast
    ├── layout.md               Above the fold, density by frequency, thumb reach, floating layers
    ├── components.md           Buttons, inputs, cards, lists, sheets, loading, errors, paywalls
    ├── motion.md               When not to animate, timing, easing, haptics
    ├── copy.md                 Interface copy and words that sound generated
    ├── web.md                  Web apps and landing pages
    ├── inspiration.md          Real references to study instead of inventing
    └── review.md               Blocking checks, the 20-point score, the report format
```

## Results

Same prompt, same model, with and without the skill: see [examples](examples/). Outputs are unedited.

## What it will not do

It will not invent your brand. Give it your logo, colors and voice and it will use them. Without them it picks calm defaults that do not look like defaults.

## Changelog

- **2.0** Mobile-first rewrite: modes, dials, 11 product presets, screen patterns, iOS, Android and cross-platform references, screenshot loop, blocking checks in review.
- **1.0** First release.

## License

MIT. Use it, fork it, change it, ship it in client work. A link back to xermio.com is appreciated, not required.

Built something with it? Tag us: @xermiolabs on X, Threads and Instagram. Issues and pull requests are welcome.

Thanks to the people whose public work shaped these rules, including Apple's Human Interface Guidelines, Material Design, Emil Kowalski on motion and Refactoring UI.
