# PPT-to-Website Alignment — 21MGO112T

This maps the uploaded **College Fest Project Management Platform** proposal (15 slides) to FestPilot. **Implemented** means browser-prototype functionality; **Illustrated** means a prebuilt visualization or editable sample metric; **Planned** means not actually built in this deliverable.

| Slide | Presentation theme | Where to demonstrate | Status / honest caveat |
|---|---|---|---|
| 1 | College Fest Project Management Platform | `index.html` | Implemented festival command center, rebranded FestPilot/AURORA ’27 as illustrative festival |
| 2 | Project selection: relevance, measurement, feasibility, learning | `charter.html` | Illustrated four selection reasons |
| 3 | Charter: problem, objectives, MVP scope/exclusions | `charter.html` | Fully documented; app provides core demonstration for events, tasks, budgets, registrations, reports; alerts are in-app summary notifications only |
| 4 | Five management phases: initiate, plan, execute, monitor, close | `schedule.html` | Illustrated five-stage lifecycle with WBS and monitoring pages |
| 5 | Stakeholder influence/interest matrix, roles | `teams.html` | Matrix and authority definitions illustrated; no live stakeholder access controls |
| 6 | Cross-functional formation & responsibilities | `teams.html` | Editable team list, responsibility table, named deliverables; sample member names |
| 7 | Scope triangle and formal change control | `charter.html`, `risks.html` | Change requests are created/approved/rejected in the demo; approvals do **not** automatically revise quantitative schedule/cost baselines |
| 8 | Prototyping, three development sprints | `schedule.html`, `tasks.html` | Stage workflow, three sprint descriptions and working task board; production role-based login remains planned |
| 9 | WBS six deliverable packages | `schedule.html` | Six WBS entries with owner, effort, acceptance criteria and completion flags |
| 10 | Six-week baseline, Gantt and critical path | `schedule.html` | Six-week reference schedule and highlighted critical-path tasks; **no algorithmic CPM recalculation** |
| 11 | Resource, budget and communication plan | `teams.html`, `budget.html` | Reference capacity (3 development staff/60%, 2 design/product, 2 QA/release, 10% time reserve), meeting cadence, budget categories and 10% budget contingency |
| 12 | Risks: severity, response, ownership, review | `risks.html` | Editable probability, impact, severity, response, owner, review date, and status; seed risks match presentation |
| 13 | Quality plan, SPI, CPI, critical defects, sprint completion | `reports.html` | Editable PV/EV/AC with working SPI/CPI calculations; targets SPI/CPI >= 0.95, critical defects 0, accepted/planned >= 85%; simulated quality checklist |
| 14 | PMIS + React/Vite/Express/Postgres/JWT/Vercel/Render stack | `charter.html`, `README.md` | Project-control concepts represented. **Actual implementation is HTML/CSS/JS/Local Storage, ready for Vercel as static site. The production stack is a planned architecture**, not implemented |
| 15 | Planned, controlled, accepted, transferred; project closure | `reports.html` | Printable/exportable status report, lessons learned, acceptance and handover checklist; actual sponsor acceptance is planned |

## Features and boundaries

**Actual browser behavior**

- Events: add, edit, delete (only if no task/registrant depends on an event), category filter and capacity checks.
- Team: add and edit members. Prevent deletion while work/risk ownership exists.
- Tasks: create, edit, delete; owner, due date, sprint, event, priority, status; search, sprint filtering and movement through Kanban columns.
- Registrations: create, remove, prevent same email enrolling twice for one event, capacity enforcement, manual check-in.
- Budget: create/edit/delete, approve/reject; approved requests cannot push commitments beyond the budget ceiling.
- Risks: edit probability, impact, severity, response strategy, owner, review date, and current status.
- Changes: submit, edit, approve/reject and capture narrative scope/time/cost impact.
- Control: recalculate SPI = EV/PV, CPI = EV/AC, and Sprint Completion = Accepted/Planned using sample measurements you can edit.
- Closure: manually tick checklists, update lessons, print and export text report, export all data JSON.

**Not implemented**

- Authentication, JWT-based role security, encrypted server sessions, actual approvals by faculty or finance personnel.
- React/Vite UI, Node/Express REST backend, PostgreSQL/Prisma database, Render backend hosting.
- Automatic email/SMS push alerts, attendance QR scanner, payment gateway, public registration links, collaborative multi-user editing.
- Integrations with GitHub Projects or cloud drive; live budget payments, real analytics, dynamic critical path / resource levelling.

## What to say to faculty

> The PPT proposes the full production architecture, while the website I am demonstrating is our interactive, browser-local MVP prototype. It demonstrates event/task coordination, registrations, budget decision workflows, project risk/change control and EVM reporting. Next we would migrate the frontend to React with a Node/Express API, PostgreSQL/Prisma persistence and JWT authorization. I have not claimed the demo's local-only approvals are real secure approvals.

This makes the relationship between project plan and demonstrated artifact explicit and defensible.
