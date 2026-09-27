# Exam Prep Planner

A single-page study companion for exam prep (26 Sep – 12 Oct 2026), covering Hindi,
English, Physics, Chemistry, Maths and Computer Science midterms plus the 12 Oct
KCET test. No build step, no dependencies — it's one self-contained `index.html`.

## Features

- **Today** — day-by-day schedule with checkable study blocks, a "NOW" highlight
  for whichever block matches the current time, a low-energy mode to trim the list
  on hard days, a quick-add box for your own tasks, and a daily reflection note.
- **Backlog** — anything left unchecked from earlier days, auto-surfaced here and
  at the top of Today until it's done.
- **Mistakes** — a Mistake → Why → Correct method → Takeaway log, filterable by
  subject and searchable.
- **Scores** — log test scores per subject with a trend sparkline.
- **Chapters** — every Physics/Chemistry/Maths chapter with completion status and
  a "flag as weak" toggle.
- **Notes** — a formula/notes scratchpad per subject.
- **Progress** — streak, hours completed, a weekly auto-recap, a weekly hours
  breakdown by subject, and a backup export.
- Focus timer (⏱) and a 25/5 Pomodoro cycle (🍅) on every task.

All progress is saved in the browser's `localStorage` — nothing leaves the device,
and nothing is saved unless this exact file is opened again in the same browser.

## Running it

No install needed — just open `index.html` in any browser.

## Hosting it for free (GitHub Pages)

1. Create a new GitHub repository and push this folder's contents to it
   (`index.html`, `manifest.json`, `service-worker.js`, and the `icon-*.png` /
   `apple-touch-icon.png` files all need to sit in the same folder).
2. In the repo, go to **Settings → Pages**.
3. Under **Source**, pick the branch (e.g. `main`) and root folder, then save.
4. GitHub will publish it at `https://<your-username>.github.io/<repo-name>/`.

## Installing it like an app

Once it's hosted (GitHub Pages or any other static host — installing does **not**
work from a `file://` path opened directly, it needs a real `http(s)` URL):

- **Android (Chrome)**: open the link → menu (⋮) → **Add to Home screen** /
  **Install app**.
- **iPhone/iPad (Safari)**: open the link → Share button → **Add to Home Screen**.
- **Desktop (Chrome/Edge)**: open the link → an install icon appears in the
  address bar → click it → **Install**.

It'll then open in its own window/icon, without browser tabs or address bar, and
`service-worker.js` caches the app shell so it still opens if you're offline
(your saved data was already local-only regardless).

## Backing up your data

Progress is per-browser. Use the **Export my progress** button on the Progress
tab occasionally, especially before clearing browser data or switching devices.

## Editing the plan

All the schedule data lives in the `const DATA = [...]` array near the top of the
`<script>` block in `index.html` — each entry is one day, with `tk` (tasks) as a
list of `{t: "time range", c: "subject code", x: "description", m: minutes}`.
Chapters live in `const CHAPTERS = [...]` the same way.
