# ✳ Enigma OS — v0.1

A small, personal, offline-friendly project command centre. Designed for laptop browsers and mobile Home Screen use.

## Get started

### Open on a laptop (simple)
1. Unzip the folder.
2. Open `index.html` in your browser.
3. The planner stores data locally in that browser. Start with the demo projects, or select **Start fresh**.

### Install on iPhone as a web app
A PWA **must be hosted over HTTPS** (or localhost for development) to support installation/offline caching properly. Opening the HTML file from the Files app is not the same as hosting it.

1. Upload the **contents** of this folder (not just `index.html`) to an HTTPS static host, such as Netlify Drop or GitHub Pages.
2. Open the hosted HTTPS URL in Safari on your iPhone.
3. Share → **Add to Home Screen** → Add.
4. Open it using the new Home Screen icon.

On a laptop, visit the same URL; supported browsers may offer **Install app**. The layout adapts automatically.

**Important:** Hosting the same app on two devices **does not synchronise your records**. Version 0.1 uses independent browser-local storage. Use Settings → Export JSON backup / Import JSON backup to transfer records manually. Cloud sync, accounts and background push notifications are **not implemented**.

## What's inside

- Project dashboard with categories, search, sort, priority, deadline and statuses
- Editable checklists: default equal weights, custom task weights, normalisation to 100%
- Expandable project inspector with notes and progress calculations
- Separate manual event countdowns
- A daily schedule timeline (add / remove items)
- Quick sleep and meal logging, weekly sleep chart
- Gentle *in-app-only* reminders while the app is open
- Automatically earned achievements
- Persistent browser-local data + JSON export / import
- Manifest, app icons and service worker for HTTPS PWA offline caching

## Data / privacy

No sign-in, tracking, external API requests or analytics. Projects, habits, sleep and meal notes are stored in `localStorage` on **that device and browser only**. Avoid storing highly sensitive health information until you have a deliberate backup/security plan. Clearing site data removes your records; export a backup periodically.

## Running locally for development

From inside this folder:

```bash
python3 -m http.server 8000
```

Visit `http://localhost:8000` in a desktop browser. Service workers require a secure context (HTTPS or localhost); this version registers caching automatically on HTTPS when deployed.

## Files

- `index.html` — page shell
- `styles.css` — responsive design
- `app.js` — state, persistence and interactions
- `manifest.webmanifest` — app installation details
- `sw.js` — offline cache
- `icons/` — Home Screen icons

## Roadmap

Cloud authentication / multi-device sync, server-based reminders, detailed nutrition analysis, recurring events and deeper project hierarchies are future features.
