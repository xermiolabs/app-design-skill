# Native apps (iOS, iPadOS, macOS, Android)

On native platforms, the best design decision is usually the platform's own. People already know how iOS and Android work. Fight that only with a strong reason.

## iOS and iPadOS

**Touch and layout**

- Tap targets at least 44 x 44pt, even when the visible icon is smaller.
- Standard side margins of 16pt; align content to the safe area, never under the home indicator or the Dynamic Island.
- Use `List`, `Form`, `NavigationStack` and system sheets before building custom versions. They come with correct spacing, swipe actions, accessibility and dark mode.

**Navigation**

- Tab bar for 3 to 5 top-level sections that people switch between. No hamburger menus.
- Navigation bar with large titles at the top level, inline titles deeper in the stack.
- Sheets for focused tasks (compose, filter, edit). Use detents (`.presentationDetents([.medium, .large])`) for lightweight ones.
- Keep the system back button and swipe-to-go-back. Never replace them with a custom arrow.

**Type, icons and color**

- Text styles with Dynamic Type (see `typography.md`). Test the largest sizes.
- SF Symbols for icons, with weight and scale matched to the adjacent text (`.imageScale(.medium)`, `.fontWeight(.semibold)`).
- Semantic colors (`.label`, `.secondaryLabel`, `.systemBackground`, `.secondarySystemBackground`, `.separator`) so dark mode, Increase Contrast and future appearance changes work.
- One tint color for the app, set once (`.tint(.brand)`).

**Liquid Glass (iOS 26 and later)**

- Glass is for the control and navigation layer that floats above content: tab bars, toolbars, floating buttons, sheets. Content itself stays solid.
- Let content scroll underneath bars; do not paint opaque custom backgrounds behind standard bars.
- Do not stack glass on glass, and do not put long text on glass.
- Adopting the system components gives you the effect; avoid custom blur effects that imitate it.
- Test with Reduce Transparency and Increase Contrast turned on.

**App icon**

- Design it as layers in Apple's Icon Composer so it adapts to light, dark, tinted and clear appearances.
- Check it at small sizes (Settings and Spotlight). Thin lines and small text disappear; one bold shape survives.

**iOS tells to avoid**

- Android-style floating action button in the corner.
- Custom back buttons, custom alerts that look like web modals.
- Tiny tap targets on icon-only buttons.
- Center-aligned list rows.
- Fixed font sizes that ignore Dynamic Type.

## macOS

- Use the sidebar, toolbar and window chrome the system provides. A Mac app should not look like a web page in a window.
- Smaller controls than iOS: regular buttons are about 22 to 28pt tall; type body is 13pt.
- Support keyboard shortcuts for every main action and show them in menus.
- Respect the menu bar: File, Edit, View, Window, Help with the standard items.

## Android (Material 3)

- Touch targets at least 48 x 48dp.
- Use Material components and color roles (primary, onPrimary, surface, surfaceContainer, outline) so dynamic color and dark theme work.
- Top app bar plus a navigation bar for 3 to 5 destinations; navigation rail on tablets.
- A floating action button is a native pattern here, for the single most common creation action.
- Support the system back gesture and predictive back; do not trap users.
- Use the type scale roles (display, headline, title, body, label) rather than raw sizes.

## Cross-platform apps (React Native, Flutter, Expo)

- Do not ship one design to both platforms unchanged. At minimum, adapt navigation, back behavior, switches, date pickers and alerts to each platform.
- Use platform-native components where the framework offers them.
- Test text scaling on both platforms.
