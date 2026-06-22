# Calm Points

A tiny local-first habit game for reducing doomscrolling without relying on willpower.

Calm Points is a phone-first Progressive Web App (PWA) designed around a simple daily score: you only need **5 out of 8 points** for a successful day, but you can still reach 8/8 when the day goes well.

The app is built to support small, realistic behaviour changes: replacing doomscrolling with low-friction actions like walking, laundry, kitchen reset, audiobook time, fellowship work, and taking the camera outside.

---

## Features

### Daily Score

Each completed action gives 1 point:

- 📸 Camera outside
- 📚 Fellowship
- 🧺 Laundry
- 🧼 Kitchen reset
- 🚶 Walk
- 📕 15 minutes of audiobook
- 📵 No doomscrolling before noon
- 📵 No doomscrolling after 10pm

A day counts as successful at **5+ points**.

### Success Levels

The app keeps the bar achievable while still rewarding better days:

- 0–2 points: Survival mode
- 3–4 points: Partial win
- 5–6 points: Successful day
- 7–8 points: Excellent day

### Streaks and XP

Calm Points tracks:

- Current streak
- Best streak
- Total XP
- Level
- Successful days

Every point gives XP, so even imperfect days still count.

### Habit-Style Graph

A colour-coded habit graph shows your recent days at a glance.

The goal is not perfection. The goal is to see patterns and build evidence that you are moving from chaos to calm.

### Doomscroll Rescue Button

When you catch yourself scrolling, tap:

> 📵 I Got Caught Scrolling

The app gives you a tiny replacement action, such as:

- Fold 5 clothes
- Wipe the counter
- Drink water
- Step outside for 2 minutes
- Photograph something blue
- Listen to 5 minutes of audiobook
- Do a tiny fellowship task

Completing a rescue action can add a point.

This turns the scrolling spiral into a recovery loop instead of a shame loop.

---

## Why Local-First?

Calm Points stores your habit data locally in your browser using `localStorage`.

That means:

- No login
- No backend
- No database
- No tracking
- No subscription
- No cloud dependency

GitHub Pages hosts the app files, but your personal habit data stays on your device/browser.

Important: if you clear your browser data, switch browsers, or change devices, your local data may not come with you automatically. Use the export/import backup tools.

---

## Files in This Project

The PWA package contains:

```text
calm-points-pwa/
  index.html
  manifest.json
  sw.js
  icons/
    icon-192.png
    icon-512.png
```

What each file does:

- `index.html` — the main app
- `manifest.json` — tells the phone how the app should appear when added to the Home Screen
- `sw.js` — service worker for basic offline/PWA behaviour
- `icons/` — app icons for Home Screen install

---

## Quick Setup: GitHub Pages

This is the easiest way to make the app work properly on iPhone.

### 1. Download and unzip the app

Download `calm-points-pwa.zip` and unzip it.

Inside, you should see:

```text
index.html
manifest.json
sw.js
icons/
```

### 2. Create a GitHub repository

1. Go to GitHub.
2. Click the **+** button.
3. Select **New repository**.
4. Name it:

```text
calm-points
```

5. Set it to **Public**.
6. Add a README if GitHub offers the option.
7. Click **Create repository**.

### 3. Upload the app files

In the new repository:

1. Click **Add file**.
2. Click **Upload files**.
3. Drag in these files/folders from the unzipped app folder:

```text
index.html
manifest.json
sw.js
icons/
```

4. Click **Commit changes**.

Your repository should look like this:

```text
calm-points/
  index.html
  manifest.json
  sw.js
  icons/
  README.md
```

Avoid accidentally uploading the whole folder as a nested folder like this:

```text
calm-points/
  calm-points-pwa/
    index.html
    manifest.json
    sw.js
    icons/
```

If `index.html` is hidden inside another folder, GitHub Pages may not open the app correctly from the main link.

### 4. Turn on GitHub Pages

1. Open the repository on GitHub.
2. Go to **Settings**.
3. Click **Pages** in the sidebar.
4. Under **Build and deployment**, set:

```text
Source: Deploy from a branch
Branch: main
Folder: /root
```

5. Click **Save**.

GitHub will give you a site URL that looks like:

```text
https://yourusername.github.io/calm-points/
```

It may take a short moment for the site to appear after the first deployment.

Official GitHub Pages documentation: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

---

## Install on iPhone

Once your GitHub Pages link is live:

1. Open the link in **Safari** on your iPhone.
2. Tap the **Share** button.
3. Tap **Add to Home Screen**.
4. Name it:

```text
Calm Points
```

5. Tap **Add**.

The app should now appear on your Home Screen like a normal app.

Official Apple guide: https://support.apple.com/en-gb/guide/iphone/iphea86e5236/ios

---

## Using the App Daily

Open Calm Points from your Home Screen.

Tick off what you completed that day.

You only need 5 points for a successful day.

A perfect 8/8 is nice, but it is not required.

The philosophy is:

> Minimum viable calm beats perfect self-improvement.

---

## Backups

Because the app is local-first, your data stays in your browser.

Use the app’s backup tools regularly:

```text
Export Backup → Save to iCloud Drive
```

To move data to another device:

```text
Import Backup → Select your saved backup file
```

Recommended rhythm:

- Export once a week
- Save the backup to iCloud Drive
- Export before clearing Safari data or changing phones

---

## iCloud Drive Notes

You can store backups in iCloud Drive.

However, iCloud Drive does **not** automatically sync the app’s browser `localStorage` between devices.

So this works:

```text
Export Backup on iPhone → Save to iCloud Drive → Import Backup on another device
```

This does not happen automatically:

```text
iPhone localStorage → iCloud sync → laptop localStorage
```

---

## Troubleshooting

### The app opens in Files instead of Safari

This happens when opening a local `.html` file directly on iPhone.

Use the GitHub Pages version instead. Safari treats the live GitHub Pages link as a website, which allows a better Home Screen/PWA experience.

### The GitHub Pages link shows a 404

Check:

- GitHub Pages is enabled under **Settings → Pages**
- Source is set to **Deploy from a branch**
- Branch is set to **main**
- Folder is set to **/root**
- `index.html` is at the top level of the repository

### My data disappeared

Possible causes:

- Browser storage was cleared
- You opened the app in a different browser
- You changed devices
- You used a different GitHub Pages URL/path

Use **Import Backup** if you previously exported your data.

### The Home Screen app does not update

Because PWAs can cache files, updates may take a refresh or two.

Try:

1. Open the GitHub Pages link in Safari.
2. Refresh the page.
3. Close and reopen the Home Screen app.
4. If needed, remove the Home Screen icon and add it again.

---

## 30-Day Experiment Idea

This app can be used as a 30-day self-experiment:

**Question:**

Can a local-first habit game reduce doomscrolling and increase intentional actions?

Track:

- Daily score
- Number of successful days
- Doomscroll rescues
- Streaks
- Fellowship consistency
- Walks
- Camera-outside days
- Mood or energy notes, if you want to journal alongside it

Suggested weekly reflection prompt:

> What did I replace scrolling with this week?

Suggested 30-day reflection prompt:

> Did my phone become more of a tool and less of a trap?

---

## Privacy

Calm Points is designed to be private by default.

The app does not need:

- A login
- A server
- Analytics
- Tracking pixels
- A database

Your data stays in your browser unless you export it yourself.

---

## License

If you want to make this open source, add a license file.

A simple choice is the MIT License, which allows other people to use, modify, and share the project while keeping attribution.

MIT License template: https://choosealicense.com/licenses/mit/

---

## Project Philosophy

Calm Points is not about becoming a perfect person.

It is about making the better action easier to start than the scrolling spiral.

The aim is:

```text
less doomscrolling
more walking
more music and books
more photography
more clean surfaces
more fellowship progress
more calm evidence
```

Small actions count.

Five points is enough.
