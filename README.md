# Task Scheduler — Automation Deployment Planner

A lightweight, browser-based task scheduling tool for planning and visualizing
automation deployments across a rolling 35-day calendar window.

Built with React (CDN), no build step required.

---

## Features

- **35-day rolling calendar** — scroll forward and backward by week
- **Drag-and-drop tasks** — reposition tasks by dragging them across day cells
- **Multi-lane stacking** — overlapping tasks stack automatically within each week row
- **Task persistence** — all data is saved to `localStorage` automatically; survives page refreshes and closed tabs
- **PDF export** — generates a landscape PDF snapshot of the current calendar view
- **Light minimalist UI** — clean, distraction-free design built for project planning contexts

---

## Deploying to GitHub Pages

### 1 — Create a new repository

Go to [github.com/new](https://github.com/new) and create a new repository.
Name it anything you like, e.g. `task-scheduler`.

### 2 — Upload the files

Upload `index.html` and `.nojekyll` to the root of the `main` (or `master`) branch.

**Option A — GitHub web UI (simplest)**

1. Open your new repository on GitHub.
2. Click **Add file → Upload files**.
3. Drag both `index.html` and `.nojekyll` into the upload area.
4. Click **Commit changes**.

**Option B — Git CLI**

```bash
git init
git remote add origin https://github.com/YOUR_USERNAME/task-scheduler.git
git checkout -b main
git add index.html .nojekyll
git commit -m "Initial commit — Task Scheduler"
git push -u origin main
```

### 3 — Enable GitHub Pages

1. Open your repository on GitHub.
2. Go to **Settings → Pages** (left sidebar).
3. Under **Source**, select **Deploy from a branch**.
4. Set **Branch** to `main` and folder to `/ (root)`.
5. Click **Save**.

GitHub will display a URL like:
```
https://YOUR_USERNAME.github.io/task-scheduler/
```

Pages typically go live within 1–2 minutes.

---

## Local Preview (no server needed)

Simply open `index.html` directly in any modern browser:

```bash
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

> **Note:** `localStorage` works when opening the file directly in a browser,
> so your tasks will persist between sessions even without a server.

---

## File Structure

```
task-scheduler/
├── index.html     ← entire application (self-contained)
├── .nojekyll      ← tells GitHub Pages to skip Jekyll processing
└── README.md      ← this file
```

---

## Data Storage

All task data is stored in the browser's `localStorage` under the key
`tqa_scheduler_v1`. To reset the schedule, open the browser console and run:

```javascript
localStorage.removeItem('tqa_scheduler_v1');
location.reload();
```

---

## Dependencies (loaded from CDN)

| Library        | Version | Purpose                     |
|----------------|---------|-----------------------------|
| React          | 18.2    | UI framework                |
| ReactDOM       | 18.2    | DOM rendering               |
| Babel Standalone| 7.22   | In-browser JSX transpilation|
| html2canvas    | 1.4.1   | Calendar screenshot capture |
| jsPDF          | 2.5.1   | PDF generation              |
| Google Fonts   | —       | DM Sans + IBM Plex Mono     |

All CDN resources are loaded from `cdnjs.cloudflare.com` and `fonts.googleapis.com`.
An internet connection is required on first load; subsequent visits may load from
the browser cache.

---

*TQA Solutions · Automation Deployment Planner*
