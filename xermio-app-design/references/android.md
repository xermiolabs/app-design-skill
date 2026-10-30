# Android (Jetpack Compose and Material 3)

Follow Material 3 and the platform's behavior first. Android users expect the system back gesture, edge-to-edge layouts and their own color theme to work.

## Layout and insets

- Draw edge to edge. Apps targeting Android 15 (API 35) are edge-to-edge by default, so handle insets deliberately.
- Use `Scaffold` and pass its `innerPadding` to the content, or apply `WindowInsets.safeDrawing` / `systemBars` padding. Content must never sit under the status bar, the navigation bar or the camera cutout.
- Touch targets at least 48 x 48dp.
- Side margins 16dp on phones; use window size classes for tablets and foldables.

## Navigation

- `NavigationBar` (bottom) for 3 to 5 destinations on phones; `NavigationRail` on medium widths; a navigation drawer only for large screens or many destinations.
- `TopAppBar` with the screen title; large or medium variants for top-level screens that collapse on scroll.
- Support the system back gesture and predictive back; never trap users in a flow.
- A floating action button is native here, for the single most common creation action on a screen.

## Nothing under the bars

- Lists inside a `Scaffold` must use the provided padding (`LazyColumn(contentPadding = innerPadding)`) so the last item clears the bottom bar.
- A persistent mini player or bottom panel goes in the `Scaffold`'s `bottomBar` slot or adds its height to the list's bottom content padding.
- Handle the keyboard with `imePadding()` on screens with text input.

## Color

- Use the Material color roles (`primary`, `onPrimary`, `surface`, `surfaceContainer`, `onSurfaceVariant`, `outline`) instead of raw hex values in components.
- Support dynamic color (Material You) on Android 12+ unless the brand truly needs fixed colors; keep a branded fallback scheme.
- Provide a dark color scheme; test both.

## Type

- Use the Material type scale roles: `displayLarge` to `labelSmall`. Map the brand font to these roles instead of using raw sizes.
- Sizes are in `sp` so they follow the user's font scale; test at 200% font scale.

## Components

- Material components first: buttons (filled for the primary action, tonal or outlined for secondary, text for tertiary), chips for filters, `ModalBottomSheet` for focused tasks, `SnackbarHost` for feedback with undo.
- Lists: `ListItem` with leading, headline, supporting and trailing content.
- Switches, sliders, date and time pickers from Material 3.

## Motion and feedback

- Use the Material motion patterns (container transform, shared axis, fade through) for navigation transitions; keep them short.
- Haptics through `LocalHapticFeedback` for meaningful moments only.

## Widgets

- Glance widgets for the app's daily glance, sized to the job: one number or one item, large.

## Android tells to avoid

- iOS-style back chevrons in the top-left with a "Back" label, iOS switches and pickers.
- Content under the navigation bar or status bar after enabling edge to edge.
- Fixed `dp` text sizes that ignore the font scale.
- A design that only works in light mode or only with one accent color.
