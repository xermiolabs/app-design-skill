# iOS, iPadOS and macOS

On Apple platforms the best design decision is usually Apple's own. People already know how iOS works. Depart from it only with a reason you can state.

## Layout and safe areas

- Respect the safe area. Nothing interactive under the status bar, the Dynamic Island or the home indicator.
- Side margins: use the system's layout margins (16pt on most iPhones, 20pt on larger ones). Lists and forms handle this for you.
- Tap targets at least 44 x 44pt, even when the visible glyph is smaller (`.contentShape(Rectangle())` and padding).
- Large titles: the content starts right under the title. If you see a big empty band between the status bar and the first content, something is adding extra padding or a spacer.

## Navigation

- `TabView` for 3 to 5 top-level sections people switch between. No hamburger menus.
- `NavigationStack` with large titles at the top level and inline titles deeper. Keep the system back button and swipe-back gesture.
- Sheets for focused tasks (compose, filter, edit), with detents for light ones: `.presentationDetents([.medium, .large])`.
- A profile or account entry sits in the top bar of the main tab (`.toolbar { ToolbarItem(placement: .topBarTrailing) { ... } }`).

## Nothing under the bars

Floating and translucent bars must not cover content.

- Standard `TabView`, `NavigationStack` and toolbars inset scroll content automatically. Custom bars do not.
- For a custom bottom bar or mini player, attach it with `.safeAreaInset(edge: .bottom) { MiniPlayer() }` so the scroll view makes room for it.
- On iOS 26 and later, put a mini player or persistent control above the tab bar with `.tabViewBottomAccessory { ... }`, and consider `.tabBarMinimizeBehavior(.onScrollDown)` for content-heavy apps.
- Check the last row of every list and every section title near the bottom: both must be fully readable when scrolled to the end.

## Liquid Glass (iOS 26 and later)

- Glass is for the control and navigation layer that floats above content: tab bars, toolbars, floating buttons, sheets. Content stays solid.
- Let content scroll under the bars; do not paint opaque custom backgrounds behind standard bars.
- No glass on glass, no long text on glass.
- Adopting the system components gives you the effect. Avoid hand-made blur effects that imitate it.
- Test with Reduce Transparency and Increase Contrast turned on.

## Type

- Use text styles (`.font(.title2)`, `.headline`, `.body`, `.footnote`) so Dynamic Type works. Default sizes are in `typography.md`.
- Test at the largest accessibility size: text wraps, rows grow, nothing truncates important information. Use `ViewThatFits` or a vertical layout when a horizontal one breaks.
- Numbers that change or align: `.monospacedDigit()`.

## Color and icons

- Semantic colors: `.primary`, `.secondary`, `Color(.systemBackground)`, `Color(.secondarySystemBackground)`, `Color(.separator)`. Dark mode and Increase Contrast then work for free.
- One app tint: `.tint(.brand)` set once at the root.
- SF Symbols for icons, matched to the adjacent text weight and scale. Use the outline variant by default and the `.fill` variant for selected states (tab bars do this automatically).

## Feedback and haptics

- Use haptics for meaningful moments only: success, warning, selection changes in pickers. In SwiftUI: `.sensoryFeedback(.success, trigger: value)`.
- Never haptics on every tap or every scroll.

## Lists, forms and controls

- `List` and `Form` for settings and data. Swipe actions with `.swipeActions`. Pull to refresh with `.refreshable`.
- System controls (`Toggle`, `Picker`, `DatePicker`, `Menu`, `ShareLink`) before custom ones.
- Context menus (`.contextMenu`) for secondary actions on items.

## Widgets and system surfaces

- If the app has a daily glance (balance, today's goal, next task, now playing), design the widget with the same job as the home screen's top section.
- Keep widgets readable at a glance: one number or one item, large; no tiny lists.

## App icon

- Build it as layers in Apple's Icon Composer so it adapts to light, dark, tinted and clear appearances.
- Check it at small sizes (Settings, Spotlight): one bold shape survives, thin lines and small text do not.

## iPad

- Use `NavigationSplitView` for list and detail. Do not stretch a phone layout to 13 inches.
- Support keyboard shortcuts and pointer hover for primary actions.

## macOS

- Use the system sidebar, toolbar and window chrome. A Mac app should not look like a phone app or a web page in a window.
- Smaller controls than iOS; body text is 13pt.
- Every main action has a menu bar item and a keyboard shortcut.

## iOS tells to avoid

- Android-style floating action buttons, hamburger menus, custom back arrows, web-style centered modals.
- Fixed point sizes that ignore Dynamic Type.
- Custom alerts for simple confirmations (use `.alert` and `.confirmationDialog`).
- Center-aligned list rows.
