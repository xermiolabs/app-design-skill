# Screen patterns

Each pattern: the job, what must be there, and the mistakes that make it look generated or work badly. Combine with the product preset.

## Onboarding

- **Job:** get the user to their first success as fast as possible.
- **Must:** show value before asking for anything (a demo, a sample result, a first task); ask only questions that change the experience and say why; three to five screens before the user is inside the product; a clear skip where possible.
- **Permissions** (notifications, location, tracking, contacts): ask in context, at the moment the feature needs them, after one sentence of explanation. Never stack permission prompts on launch.
- **Account:** sign-up after the first value moment when the product allows it. Offer Sign in with Apple on iOS if you offer other social logins (Apple requires it in many cases).
- **Mistakes:** feature carousels with illustrations, a sign-up wall first, asking for name, birthday and goals before showing anything.

## Paywall

- **Job:** help the user decide to pay, honestly.
- **Must:** lead with the outcome in the user's words; two or three plans at most with one highlighted; price, period and renewal stated plainly; trial length and what happens after it; a visible close or "Not now"; Restore Purchases, Terms and Privacy links (required on iOS).
- **Layout:** the plan picker and the main button in the lower half; benefits above as three to five short lines, each one a result, not a feature.
- **Mistakes:** hidden close buttons, fake discounts, countdown timers, tiny renewal terms, a wall of checkmarks.

## Home and feed

- **Job:** answer why the user opened the app today.
- **Must:** the answer above the fold (resume, today's number, what's new for me); a clear path to the primary action; profile or account entry in the top bar; density that matches how often the screen is opened.
- **Mistakes:** a greeting taking the top third of the screen, one hero card pushing everything else below the fold, a dashboard of equal cards, section titles hidden under the tab bar or mini player.

## List

- **Job:** find and act on one item among many.
- **Must:** rows with a fixed leading column (icon, avatar, thumbnail), one primary line, one quiet secondary line, one trailing element (value, chevron, switch or menu); swipe actions for the common ones; search or filter when there are more than about 20 items; sections only when they help scanning.
- **Mistakes:** cards for every row, center-aligned text, three lines of metadata, no empty or "no results" state.

## Detail

- **Job:** understand one thing fully and act on it.
- **Must:** the key facts at the top (title, the number that matters, status); the main action in a bottom bar or near the top, not at the end of a long scroll; related actions in a menu, not a row of five buttons.
- **Mistakes:** a huge image with the title over it and no scrim, actions scattered through the page.

## Search

- **Job:** get to the right thing in as few keystrokes as possible.
- **Must:** focus the field and open the keyboard on entry when search is the screen's purpose; recent searches and suggestions before typing; results as you type; a "no results" state that suggests what to try.
- **Mistakes:** a search screen that is a second home screen of banners, results that clear when the keyboard closes.

## Settings

- **Job:** change one thing and leave.
- **Must:** native grouped list (iOS `Form`/`List`, Material list on Android); groups ordered by how often they are used; account and subscription at the top; destructive actions (log out, delete account) at the bottom and confirmed. Apps that allow account creation must allow account deletion in the app on iOS.
- **Mistakes:** custom-styled settings that look like a web page, every row with a colored icon, toggles that need a save button.

## Profile and account

- **Job:** see and edit who I am in the app.
- **Must:** avatar, name, the stats that matter to this product, an edit action, and a path to settings.
- **Mistakes:** vanity stats nobody asked for, editing hidden behind three menus.

## Auth (sign in, sign up)

- **Must:** platform sign-in options first where they exist (Sign in with Apple, Google); email with a magic link or code as the fallback; correct keyboard types and autofill (`textContentType`, `autofillHints`); passwords with show/hide; errors next to the field in plain words.
- **Mistakes:** a password field with no autofill, forcing account creation before any value, legal text in tiny gray type.

## Checkout

- **Must:** order summary with every fee visible before the final button; Apple Pay or Google Pay first where available; address and payment autofill; one primary button that states the total ("Pay $24.80").
- **Mistakes:** fees revealed on the last step, multi-page forms, "Submit".

## Empty, loading, error and offline states

- **Empty:** what this place is, why it is empty, the one action to fill it.
- **Loading:** skeletons shaped like the real content for anything over about 300ms; progress with words for long tasks.
- **Error:** what happened and what to do, with a retry; keep what the user typed.
- **Offline:** show cached content with a quiet banner; queue actions and sync later where possible.
- **Mistakes:** a sad cloud with "No data", spinners in the middle of empty screens, errors as alerts for things that could be inline.
