# Project Dashboard

A lightweight project planning dashboard with Gantt chart, capacity tracking, fit finder, and deadline-based backwards planner. No backend required — runs entirely in the browser and saves data to localStorage.

---

## Features

- **Gantt chart** — all projects on one timeline, colour-coded by project and phase
- **Capacity view** — monthly utilisation bars showing days free, flagged by fiscal quarter (Sept 1 year start)
- **Fit finder** — finds open windows in your calendar where a new project would fit
- **Deadline planner** — enter a final deadline, get a full phase timeline calculated backwards; adjust any duration and dates recalculate live
- **Project tabs** — per-project phase editor with start/end dates, notes, and status
- Weekly / Monthly / Quarterly timeline views
- Export to CSV (per-project or all projects)
- Link to your Google Sheet
- Dark mode support
- Data saved automatically to browser localStorage

---

## Setup on GitHub Pages (free, ~5 minutes)

### Step 1 — Create a GitHub account
Go to [github.com](https://github.com) and sign up if you don't already have one.

### Step 2 — Create a new repository
1. Click the **+** icon in the top right → **New repository**
2. Name it `project-dashboard` (or anything you like)
3. Set it to **Public** (required for free GitHub Pages)
4. Click **Create repository**

### Step 3 — Upload the file
1. On your new repo page, click **uploading an existing file**
2. Drag and drop `index.html` into the upload area
3. Scroll down and click **Commit changes**

### Step 4 — Enable GitHub Pages
1. Go to your repo's **Settings** tab
2. In the left sidebar, click **Pages**
3. Under **Branch**, select `main` and click **Save**
4. Wait ~60 seconds, then refresh — you'll see a green banner with your URL:
   `https://YOUR-USERNAME.github.io/project-dashboard`

Share that URL with your team and everyone can use the same dashboard. Each person's data saves to their own browser.

---

## Updating the dashboard later

To update with a new version of `index.html`:
1. Go to your repo on GitHub
2. Click `index.html` in the file list
3. Click the pencil (edit) icon, or drag a new file to replace it
4. Commit — GitHub Pages updates automatically within a minute or two

---

## Data & privacy

- All project data is stored in your browser's **localStorage** — nothing is sent to any server
- Each browser/device has its own copy of the data
- Clearing browser data will erase the dashboard — export a CSV backup periodically
- If you want shared data across your whole team, the next step would be connecting to a backend (e.g. a Google Sheet via Apps Script, or a simple database)

---

## Customising phase defaults

The default phase durations (used by the deadline planner) are set near the top of `index.html`:

```js
const DEFAULT_PHASE_DURATIONS = {
  Request:     3,
  Planning:    5,
  Recruitment: 7,
  Research:    10,
  Analysis:    5,
  Reporting:   5
};
```

Edit these numbers to match your team's typical timings and save the file.

---

## Google Calendar integration

Full two-way Google Calendar sync requires OAuth authentication, which needs a small backend or Google Apps Script. If you'd like this set up, ask Claude to build a Google Apps Script version that reads from your Google Sheet and pushes phase dates to a calendar.
