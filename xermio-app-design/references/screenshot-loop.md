# Screenshot loop

You cannot judge a design you have not seen. After building, run the app, capture screenshots, look at them, fix, and capture again. Two or three loops are normal.

## Capture

**iOS Simulator**

```bash
xcrun simctl list devices booted            # find the booted simulator
xcrun simctl io booted screenshot home.png   # capture the current screen
xcrun simctl ui booted appearance dark       # switch to dark mode, capture again
xcrun simctl ui booted appearance light
```

Build and launch from the command line when needed:

```bash
xcodebuild -scheme <Scheme> -destination 'platform=iOS Simulator,name=iPhone 16' build
xcrun simctl install booted <path/to/App.app>
xcrun simctl launch booted <bundle.id>
```

For SwiftUI previews, use `#Preview` with several states (empty, loaded, error, large text) side by side, and render them in Xcode if a simulator run is not possible.

**Android Emulator**

```bash
adb devices                                   # find the emulator
adb exec-out screencap -p > home.png          # capture the current screen
adb shell "cmd uimode night yes"              # dark mode, capture again
adb shell "cmd uimode night no"
adb shell settings put system font_scale 2.0  # largest text, capture again
adb shell settings put system font_scale 1.0
```

**Expo and React Native**

Run on the iOS Simulator or Android Emulator and use the commands above. For a quick layout check, the web build (`npx expo start --web`) can be captured with Playwright, but always confirm on a real simulator before calling it done.

**Web**

```js
const { chromium } = require('playwright');
const browser = await chromium.launch();
const page = await browser.newPage({ viewport: { width: 393, height: 852 }, deviceScaleFactor: 3 });
await page.goto('http://localhost:3000');
await page.screenshot({ path: 'mobile.png', fullPage: true });
```

## What to capture

For each main screen:

1. Default state with realistic content, light mode.
2. Dark mode.
3. Largest text size (iOS: Accessibility XXXL; Android: font scale 2.0).
4. Empty state, loading state, error state.
5. Scrolled to the bottom, to check nothing hides under bars.

## What to look for

Look at each screenshot for ten seconds before reading any code:

- What did my eye land on first? Is that the job of the screen?
- Is there an empty band at the top or between sections?
- Is anything cut off, overlapping or hidden under a bar, the notch or the keyboard?
- Is any text hard to read (on images, gray on gray, too small)?
- Does it look like this platform, and not like a web page or the other platform?
- Does it look like a specific product, or like a copy of the category leader?
- How many things compete for attention? There should be one signature element.

Write down every issue, fix them, and capture again. Include the final screenshots in your report to the user.
