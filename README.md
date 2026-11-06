# FestPilot — College Fest Project Management Platform

A polished, responsive **multi-page project-management prototype** for a college fest, built to demonstrate the proposal in `College_Fest_Platform_Project_Management_Presentation-2.pptx` (21MGO112T, SRM Institute of Science and Technology).

**Important:** This is a functional **browser-local prototype**, not the production React/Express/PostgreSQL/JWT system proposed on slide 14. Data is illustrative, approvals are simulated, and no real financial transactions, email alerts, secure logins, or multi-device sync are performed. This distinction is intentional and must be communicated clearly in a viva.

## Run locally (VS Code)

1. Extract the ZIP.
2. Open the **FestPilot** folder (the one containing `index.html`) in VS Code.
3. Use the **Live Server** extension: right-click `index.html` → **Open with Live Server**. Alternatively, with Python installed, run:

   ```bash
   python -m http.server 5500
   ```

4. Visit `http://localhost:5500/index.html` (or the address displayed by Live Server).

**Use a local HTTP server or Vercel, not `file://` double-click mode**, because browser local-storage behavior can differ across individual file URLs.

## The ten distinct HTML pages

| Page | File | Functionality |
|---|---|---|
| Command center | `index.html` | Fest countdown, KPI cards, upcoming events, task progress, actions, high-level SPI/CPI |
| Charter & scope | `charter.html` | Project selection, charter objectives, MVP scope and exclusions, governance |
| Events & venues | `events.html` | Add/edit/delete events, category filters, venue/date/capacity tracking |
| Task board | `tasks.html` | Add/edit/delete tasks, sprint filters, search, assign owners, move across status columns |
| Teams | `teams.html` | Add/edit/remove team members, stakeholder matrix, communication plan and responsibility matrix |
| Registrations | `registrations.html` | Add/remove participant records, prevent duplicate emails per event, enforce capacity, check in/out |
| Schedule & WBS | `schedule.html` | Six-week sample Gantt, highlighted critical path, WBS packages, editable milestone ticks, sprint plan |
| Budget approvals | `budget.html` | Submit/edit/delete/approve/reject requests, protect budget ceiling, breakdown charts |
| Risks & change | `risks.html` | Add/edit/resolve risks with probability/impact/response/owner/review, request and decide changes |
| Reports & closure | `reports.html` | Edit EV/PV/AC, calculate SPI/CPI/sprint completion, quality and handover checklists, export/print |

## Architecture

```text
10 separate HTML pages
  ├── styles.css      Shared responsive styling, festival-inspired visual design
  ├── app.js          Shared app logic, per-page renderer, form handling and KPIs
  └── assets/         Favicon and optimized image from the user's presentation
             ↓
Browser localStorage ('festpilot_aurora_demo_v2')
             ↓
Shared demo records across pages on the same website origin
```

All page navigation uses ordinary `<a href="...html">` links, so these are **actual separate HTML files**, not fake tabs. Each page loads the same `app.js`, which uses the `data-page` attribute to render that page's content. Event records connect to tasks and registrations through `eventId`. Tasks and risks identify their responsible owners.

The initial demo data is for an invented **AURORA ’27** college fest on 19–21 March 2027. People, budgets, registrations, progress values, dates and approvals are **illustrative**; replace them with actual project facts before presenting them as factual information.

## Implemented vs. proposed

**Implemented now:** Multi-page interface, responsive CSS, event/task/team CRUD, sprint board, calendar-based scheduling data, attendee limits, manual check-in, simulated budget approval, risk/change records, local persistent data, calculated SPI/CPI, printable/text reports, JSON backup, quality and closure checklists.

**Conceptual or simulated:** Role authority, sponsor sign-off, alert notification indicators, time/cost baselines, six-week Gantt and critical-path marking, and the sample performance measures. Budget approval is a local status change; no authentication or audited authorizer exists.

**Proposed future full stack from PPT slide 14:**
- React + Vite for the interface
- Node.js + Express for secure APIs
- PostgreSQL + Prisma for multi-user persistent data
- JWT authentication plus server-enforced role-based authorization
- Vercel (frontend) + Render (backend)
- GitHub Projects/shared drive/meeting logs as external PMIS tools

The Vercel-ready app in this ZIP is **vanilla HTML/CSS/JavaScript** so it is easily demonstrated and deployed without npm, React, or a backend. Do **not** say it already implements the slide-14 stack.

## Deploy to Vercel from GitHub

1. Create a public GitHub repository (for example, `festpilot`) **without** an initial README.
2. In VS Code's terminal, from **this FestPilot folder**, run:

   ```bash
   git init
   git branch -M main
   git add .
   git commit -m "Build college fest project management prototype"
   git remote add origin https://github.com/Sangat-Singh/festpilot.git
   git push -u origin main
   ```

3. Visit `https://vercel.com/new`, import the GitHub repository and choose **Other** as the framework preset.
4. Root directory: `./`. No build command, framework install, environment variables or Node.js server needed.
5. Deploy. Vercel serves the root `index.html` and the other named `.html` pages.
6. Check the deployed website's tasks, registration, forms, and responsiveness.

If Git or remote configuration already exists, inspect `git status` and `git remote -v` first instead of blindly repeating repository setup commands.

## Data and privacy

- Browser `localStorage` is per browser/device/origin. Opening the same website on another laptop does **not** sync data.
- JSON export lets you preserve a backup; there is no JSON import feature.
- Reset demo restores the illustrative starting records and deletes the local changes for this website origin.
- **Do not enter real student personal data** into a browser-only demo.
- The design uses optional Google-hosted fonts with system-font fallbacks. All critical functionality remains local/offline.

## Basic automated test coverage

Rendered all ten pages with no JavaScript runtime errors. Browser-automation checks exercised task add/search/move, event creation/filtering, budget request/approval, participant registration/check-in, risk/change submissions, metric editing, report checklist changes and the mobile navigation drawer. Actual Vercel production deployment has **not** been performed and must be verified separately.

## Additional study files

- `PPT_ALIGNMENT.md`: Slide-by-slide mapping between this site and the uploaded presentation.
- `VIVA_GUIDE.md`: Demo sequence, core answers and 30 anticipated viva questions.
- `MINIMAL_PROMPT_EXAMPLE.txt`: A concise **example prompt** for recreating this prototype; it is not a claimed transcript of development.

