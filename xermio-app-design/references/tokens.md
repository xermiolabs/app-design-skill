# Tokens

Write tokens before building. A token is a named decision. If a value is not in the token list, it does not go in the design.

## Spacing

One scale, based on 4:

```
4  8  12  16  24  32  48  64  96
```

- 4 and 8: inside small components (icon to label, chip padding).
- 12 and 16: inside cards, list rows, form fields; screen margins on phones (16).
- 24 and 32: between groups inside a section.
- 48 to 96: between sections on web pages.

Rule of thumb: the space between two groups should be at least twice the space inside each group.

## Radius

Pick one personality and stay in it.

| Personality | Small (inputs, chips) | Medium (buttons, cards) | Large (sheets, modals) | Feels |
| --- | --- | --- | --- | --- |
| Sharp | 4 | 6 | 8 | Technical, editorial, finance |
| Balanced | 6 | 10 | 16 | Most SaaS and consumer apps |
| Soft | 10 | 14 | 24 | Playful, wellness, kids |

Nested corners: inner radius = outer radius minus the padding between them. A 16px card with 8px padding holds an 8px inner element. Equal radii on nested shapes look wrong.

Full pill shapes are fine for buttons and chips. They are not fine for cards.

## Elevation

Two levels at most.

```css
--shadow-1: 0 1px 2px rgb(0 0 0 / 0.06), 0 1px 1px rgb(0 0 0 / 0.04);
--shadow-2: 0 8px 24px rgb(0 0 0 / 0.10), 0 2px 6px rgb(0 0 0 / 0.06);
```

- Level 1: cards that need to lift slightly off a tinted background. On a white page, prefer a 1px border instead.
- Level 2: menus, popovers, modals, anything floating above the page.
- In dark mode, show elevation with a lighter surface color, not a shadow.

## Neutral palettes

Pick warm or cool. Never mix them.

Cool neutral (pairs with blue, teal, green accents):

```
50  #F7F8FA   100 #EEF0F3   200 #DDE1E7   300 #C4CAD3   400 #9AA3AF
500 #6B7482   600 #4E5664   700 #373D48   800 #22262E   900 #14171C   950 #0B0D10
```

Warm neutral (pairs with orange, coral, olive, gold accents):

```
50  #F8F7F4   100 #F0EEE9   200 #E2DED6   300 #CBC5BA   400 #A39C90
500 #77706A   600 #58524D   700 #3E3A36   800 #282624   900 #181716   950 #0E0D0C
```

Text on light backgrounds: primary 900, secondary 600, tertiary 500 (passes 4.5:1 on white, but not on the 50 surface, so keep it for white backgrounds or large text). Dividers and card borders 200. Input and control borders around `#868F9C` (3:1 on white) so fields are visible. Subtle fills 50 or 100.

## Accent

One hue with three working shades:

- **Base** for primary buttons and active states.
- **Hover/pressed** about 8 to 12 percent darker.
- **Tint** at 8 to 12 percent opacity for selected rows, focus halos and soft badges.

Good starting accents that do not look like defaults, each passing 4.5:1 with a white label: `#3155ED` (ultramarine, 5.8:1), `#0E7C66` (deep green, 5.1:1), `#C9431F` (coral, 4.9:1), `#966214` (ochre, 5.2:1). Brighter versions of coral or ochre are fine for icons and tints, but not behind white text.

## Starter set as CSS variables

```css
:root {
  --space-1: 4px; --space-2: 8px; --space-3: 12px; --space-4: 16px;
  --space-5: 24px; --space-6: 32px; --space-7: 48px; --space-8: 64px; --space-9: 96px;

  --radius-s: 6px; --radius-m: 10px; --radius-l: 16px;

  --bg: #FFFFFF; --surface: #F7F8FA; --border: #DDE1E7;
  --text: #14171C; --text-2: #4E5664; --text-3: #6B7482;
  --border-input: #868F9C;
  --accent: #3155ED; --accent-hover: #2546D4; --accent-tint: rgb(49 85 237 / 0.10);
  --success: #1A7F52; --warning: #966214; --danger: #C8382C;

  --font: "Inter", "Geist", system-ui, sans-serif;
  --text-xs: 12px; --text-s: 14px; --text-m: 16px; --text-l: 20px; --text-xl: 24px; --text-2xl: 32px; --text-3xl: 48px;
}
```

## Starter set in Tailwind (v3 config or v4 @theme)

Replace the defaults instead of layering on top of them. In Tailwind v4:

```css
@theme {
  --color-accent: #3155ED;
  --color-accent-hover: #2546D4;
  --color-ink: #14171C;
  --color-muted: #4E5664;
  --color-line: #DDE1E7;
  --color-surface: #F7F8FA;
  --radius-card: 10px;
  --font-sans: "Inter", system-ui, sans-serif;
}
```

Then use `bg-accent`, `text-ink`, `text-muted`, `border-line`, `rounded-card`. Do not use `indigo-*`, `purple-*` or `violet-*` unless that is the brand.

## Starter set in SwiftUI

Prefer system semantics so dark mode and accessibility work for free:

```swift
enum Space { static let xs: CGFloat = 4, s: CGFloat = 8, m: CGFloat = 16, l: CGFloat = 24, xl: CGFloat = 32 }

extension Color {
    static let brand = Color("Brand")              // asset catalog color with light and dark variants
    static let textPrimary = Color(.label)
    static let textSecondary = Color(.secondaryLabel)
    static let surface = Color(.secondarySystemBackground)
}

// Type: use text styles, not fixed sizes, so Dynamic Type works
Text("Balance").font(.headline)
Text("$2,480.12").font(.largeTitle.weight(.semibold)).monospacedDigit()
```
