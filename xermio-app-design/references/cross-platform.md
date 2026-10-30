# Cross-platform apps (React Native, Expo, Flutter)

One codebase, two platforms, two sets of user expectations. Share the brand and the logic; adapt the platform behavior.

## What to adapt per platform

| Element | iOS | Android |
| --- | --- | --- |
| Back | Chevron + swipe from the left edge | System back gesture, arrow in the top app bar |
| Primary creation action | Button in the nav bar or a bottom bar | Floating action button is fine |
| Switches, pickers, date pickers | iOS style | Material style |
| Alerts and action sheets | Alert / action sheet | Material dialog / bottom sheet |
| Tab bar | Tab bar with SF-style icons, labels always shown | Navigation bar with Material icons, active indicator |
| Haptics | Light, for success and selection | Sparing |
| Fonts | System font (SF Pro) unless branded | System font (Roboto or device font) unless branded |

At minimum adapt navigation, back behavior, switches, date pickers and alerts. A single Android-looking app on iOS (or the reverse) reads as cheap.

## React Native and Expo

- Safe areas: wrap the app in `SafeAreaProvider` and use `useSafeAreaInsets()` from `react-native-safe-area-context`. Do not hard-code status bar heights.
- Navigation: React Navigation or Expo Router with native stack (`@react-navigation/native-stack`) and native bottom tabs, so transitions, large titles and back gestures are platform-native.
- Lists: `FlatList` or `FlashList` with `contentContainerStyle={{ paddingBottom: insets.bottom + tabBarHeight }}` (use `useBottomTabBarHeight()`) so nothing hides under the tab bar or a mini player.
- Keyboard: `KeyboardAvoidingView` (behavior `padding` on iOS) or a keyboard controller library for chat and forms.
- Platform differences: `Platform.select({ ios: ..., android: ... })` for the elements in the table above.
- Text: allow font scaling (do not set `allowFontScaling={false}` on body text); test at the largest system size.
- Icons: SF Symbols on iOS (for example via `expo-symbols`) and Material Symbols on Android, or one consistent cross-platform set.
- Haptics: `expo-haptics` for success and selection only.
- Images: `expo-image` with placeholders that match the final size, so layouts do not jump.

## Flutter

- Use `SafeArea`, `MediaQuery.paddingOf(context)` and `Scaffold` slots for bars so content clears them.
- Material 3 (`useMaterial3: true`) on Android; Cupertino widgets or adaptive constructors (`Switch.adaptive`, `showAdaptiveDialog`) where iOS users expect native behavior.
- Theme with `ColorScheme.fromSeed` plus your brand overrides, and a dark scheme.
- Text: use the theme's `textTheme` roles and respect `MediaQuery.textScalerOf`.

## Shared design system

- One token file (colors, spacing, radius, type roles) consumed by both platforms; platform-specific values only where behavior differs.
- Name tokens by role (`surface`, `textSecondary`, `accent`), not by value (`gray200`), so dark mode and future rebrands are a token change.
