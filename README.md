# Xermio App Design Skill

A free skill for Claude Code, Claude and other coding agents that makes AI-built apps stop looking AI-built.

Ask an agent for a screen and you get the same thing every time: indigo buttons, a purple gradient, six feature cards with emoji, light gray text you can barely read. That is not bad taste. It is the absence of decisions. This skill gives the agent the decisions a senior product designer would make: a token system, a type scale, color discipline, platform conventions for iOS and Android, and a strict review score before anything ships.

Made by [Xermio](https://xermio.com), an independent product design and engineering studio.

## Results

Same prompt, same model, with and without the skill: see [examples](examples/). Outputs are unedited.

## What is inside

```
xermio-app-design/
├── SKILL.md                  The workflow, ten rules, and the list of AI tells
└── references/
    ├── tokens.md             Ready-made spacing, radius, color and type tokens (CSS, Tailwind, SwiftUI)
    ├── typography.md         Font choices, web scale, iOS text styles, numbers
    ├── color.md              Palette building, contrast, dark mode, charts
    ├── layout.md             Grids, the squint test, dashboards, tables, forms, landing pages
    ├── native.md             iOS (incl. Liquid Glass), macOS, Android, cross-platform
    ├── web.md                Tailwind without the Tailwind look, shadcn, responsive, performance
    ├── components.md         Buttons, inputs, cards, empty states, onboarding, paywalls
    ├── motion.md             When to animate at all, durations, easing, practical rules
    ├── copy.md               Interface copy, landing page copy, words that sound generated
    ├── inspiration.md        Real references to study instead of inventing
    └── review.md             A 20-point review score the agent must pass before showing you the result
```

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

Claude picks it up automatically when you ask for UI work.

**Claude (web and desktop apps)**

Zip the `xermio-app-design` folder and upload it as a custom skill in Claude's settings (Skills must be turned on for your account).

**Other agents (Cursor, Codex, Gemini CLI and others)**

Most agents that support the open Agent Skills format read a folder with a `SKILL.md`. Put the folder where your agent looks for skills, or paste `SKILL.md` into your project rules and keep the `references` folder next to it.

## How to use it

You do not need special commands. Ask for UI work as usual. These prompts get the most out of it:

```
Build the settings screen for my iOS habit app. Use the xermio-app-design skill.
```

```
Here is a screenshot of my dashboard. Review it with the xermio-app-design review score and fix everything below 2.
```

```
Create a token set for a calm personal finance app: warm neutrals, one green accent, light and dark mode.
```

```
This landing page looks AI-made. Find every AI tell and rewrite it.
```

```
Design the empty, loading and error states for this list.
```

## What it will not do

It will not make design decisions that need your brand: your logo, your exact colors, your voice. Give it those and it will use them. Without them it picks calm, neutral defaults that do not look like defaults.

## License

MIT. Use it, fork it, change it, ship it in client work. A link back to xermio.com is appreciated, not required.

Built something with it? Tag us: @xermiolabs on X, Threads and Instagram. Issues and pull requests are welcome at github.com/xermiolabs/app-design-skill.

Thanks to the people whose public work shaped these rules, including Emil Kowalski on motion, Refactoring UI, Apple's Human Interface Guidelines and Material Design.
