# Components

## Buttons

- Heights: 32 (compact), 40 (default web), 44 to 50 (touch and primary mobile actions). Pick one per context and keep it.
- One primary button per view. Everything else is secondary (outline or tinted) or tertiary (text only).
- Labels are verbs with an object: "Create invoice", "Save changes", "Start free trial". Not "Submit", "OK", "Click here".
- Destructive actions in the danger color, and confirm them with the object named ("Delete 3 files?").
- Loading state keeps the button width and shows a spinner or progress inside; the label can change to "Saving...".
- Icon-only buttons need a tooltip on web and an accessibility label everywhere.

## Borders, shadows, icons and images

- Borders for structure (separating parts of a layout), shadows for depth (things floating above the page). Do not use both strongly on the same element.
- About 12px between neighboring bordered controls (a row of inputs, a button group with gaps).
- Icons: outline by default, filled for the active or selected state. Match the icon stroke to the weight of the text beside it.
- Images and screenshots get a thin neutral outline (for example `1px rgb(0 0 0 / 0.08)`, inside the edge) so white images do not bleed into a white page.

## Inputs

- Visible label above, optional helper text below, error text replacing the helper in the danger color.
- Same height as buttons in the same row.
- Border 1px in a neutral that reaches 3:1 against the background (for example `#868F9C` on white); focus shows a ring in the accent.
- Use the right keyboard on mobile (`type="email"`, `inputmode="numeric"`, `.keyboardType(.decimalPad)`).
- Never clear what the user typed after an error.

## Cards

- Only when the content is a distinct, clickable or movable object (a project, a product, a file).
- Padding 16 to 24, radius from tokens, border or a very soft shadow, not both strong.
- One title, one supporting line, one action. A card with four buttons is a page.
- No cards inside cards. No card just to hold a heading.

## Lists and rows

- Row height 44 to 56 on touch, 36 to 48 on desktop.
- Leading element (icon, avatar, thumbnail) aligned to a fixed column; text aligned to one left edge.
- Primary text in primary color, secondary text below or to the right in secondary color.
- Trailing area for one thing: a value, a chevron, a switch, or a menu.

## Empty states

Every empty state answers three questions:

1. What is this place? ("Invoices you send will appear here.")
2. Why is it empty? (Nothing yet, or no results for a filter.)
3. What do I do now? (One primary button, or "Clear filters".)

A small illustration or icon is optional. A sad cloud with "No data" is not an empty state.

## Loading

- Under 300ms: show nothing.
- 300ms to 2s: skeletons shaped like the real content.
- Over 2s: progress with words ("Importing 1,240 contacts...").
- Optimistic updates for small actions (like, check, reorder), with an undo on failure.

## Success

- Confirm that something worked, close to where it happened: the button changes to "Saved", the row updates, a short toast for background work.
- After a big moment (first project created, payment done), show the next useful step, not just a checkmark.

## Errors and toasts

- Say what happened and what to do, in plain words: "Couldn't save. Check your connection and try again." Never "Error 500" alone.
- Inline errors for forms; toasts for background events; full-page errors only when the page cannot work.
- Toasts disappear after 4 to 6 seconds, except errors that need action.

## Modals and sheets

- Use for short, focused tasks. If it needs scrolling and tabs, it should be a page.
- Clear title, the primary action bottom right (web) or as the main button (mobile), an obvious way out (Cancel, close, swipe down).
- Never open a modal on page load.

## Onboarding

- Show value before asking for anything. A demo, a sample result or a first small task before sign-up.
- Ask only what changes the experience, and say why ("So we can set your daily goal").
- Three to five screens at most before the user is inside the product.
- Permissions (notifications, location, tracking) asked in context, right when the feature needs them, with a sentence of explanation first.

## Paywalls

- Lead with what the user gets, in their words, not a feature list.
- Two or three plans at most; highlight one (usually annual) and show the saving honestly ("Save 40%").
- Price, period and renewal terms clear and readable. Trial length and what happens after it, stated plainly.
- A visible close or "Not now" option. Dark patterns get apps rejected and refunds requested.
- On iOS, include Restore Purchases and links to your Terms and Privacy Policy.

## Navigation

- 3 to 5 top-level destinations. More than that means the information architecture needs work.
- The current location is always visible (active tab, highlighted sidebar item, page title).
- Labels are nouns the user would say ("Invoices", "Clients"), not internal names.
