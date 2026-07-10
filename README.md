# Reader's Ledger — PWA (Progressive Web App)

A strict reading-streak tracker with a built-in PDF viewer, packaged to
install straight onto your phone's home screen — no computer, no app store,
no command line required.

## Files in this folder
- `index.html` — the whole app (streak tracker + PDF reader)
- `manifest.json` — tells the phone this is installable (name, icon, colors)
- `sw.js` — service worker, caches the app so it still opens with no signal
- `icon-192.png`, `icon-512.png` — home screen icons

## How to install it on your phone (no computer needed)

### 1. Host the files somewhere with `https://`
Phones can't "Add to Home Screen" a page unless it's served over https.
Easiest free option, done entirely from your phone's browser:

1. Go to **github.com** and sign up (free) if you don't have an account
2. Tap **New repository** → name it `readers-ledger` → set to **Public** → Create
3. Tap **Add file → Upload files**, unzip this package on your phone, and
   upload all 5 files listed above
4. Go to the repo's **Settings → Pages**, set Source to your main branch, **Save**
5. Wait about a minute — you'll get a link like:
   `https://yourname.github.io/readers-ledger/`

### 2. Install it
- **iPhone (Safari):** open the link → tap **Share** → **Add to Home Screen**
- **Android (Chrome):** open the link → tap **⋮** menu → **Install app**

It now sits on your home screen with its own icon, opens full-screen with
no browser bar, and keeps working offline once loaded.

## How your data is stored
Everything — streaks, daily page counts, settings — is saved with
`localStorage`, right on your device. Nothing is sent anywhere, and it isn't
tied to the GitHub host once installed.

## About the PDF you read
The PDF itself isn't stored inside the app (only text/small data can persist
this way). Each time you open the app, use the "Open a PDF" button to pick
the file from your phone again — your page progress and streak for that book
are remembered and pick up right where you left off.

## Updating the app later
If you ever want to change something in `index.html`, just re-upload the
changed file(s) to the same GitHub repo (Add file → Upload files → same
filenames to overwrite). The next time you open the installed app, it'll
pick up the new version (you may need to fully close and reopen it once).
