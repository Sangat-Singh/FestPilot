# FestPilot — Viva Preparation

## 90-second introduction you can say

> My project is **FestPilot — a College Fest Project Management Platform** based on our Project Management course proposal. College fest coordination often becomes fragmented across chats, spreadsheets and calls. We developed a multi-page prototype that centralizes fest events, task ownership, team responsibilities, registrations, budget requests, project risks, schedule information and performance reports. A student organizer can create an event, assign a task, register a participant, approve a sample budget request and inspect project health. We followed the project-management lifecycle: initiation, planning, execution, monitoring and closing. The demo uses HTML, CSS and JavaScript, with Local Storage to keep data after refresh on the same website origin. The presentation also proposes a production migration to React, Express, PostgreSQL and JWT roles; those backend features are not yet implemented. Our prototype demonstrates the main processes and how they can be measured.

## Six-minute demonstration route

1. **Command center:** Explain the problem and show live counts, task progress, budget and upcoming events.
2. **Charter & scope:** Show objectives O1–O4, what is included/excluded in MVP, sponsor authority and project selection rationale.
3. **Events & Tasks:** Add a sample event, create a task, assign its owner, choose Sprint 3 and advance the task from To do → In progress → Done.
4. **Registration & Budget:** Register a dummy participant and check them in. Add a small budget request and approve it; show approved amount and balance update.
5. **Schedule & Risks:** Point to the six-week Gantt and critical path. Add a risk with probability, impact, response, owner and review date, then demonstrate a scope change request.
6. **Reports:** Explain `SPI = EV / PV`, `CPI = EV / AC`, `Sprint Completion = Accepted / Planned`. Edit a value and show the automatic recomputation. Show quality/closure checklist and export a report.

Use **sample names and email addresses** in the demo. Do not enter real participant personal details.

## 30 common viva questions and short answers

1. **What is your project?** A college fest project coordination prototype that organizes events, work, resources and project control.
2. **Why choose this project?** Relevant real-world scheduling, ownership and budgeting issues; measurable outcomes; feasible MVP; clear Project Management learning.
3. **What problem are you solving?** Information fragmentation across chats, spreadsheets and calls leading to lost ownership and schedule/cost visibility.
4. **Who uses it?** Project manager, product owner, event coordinators, volunteers, finance/venue teams and participants (the demo does not securely log these roles in).
5. **What is the Project Charter?** A document authorizing the project and stating its problem, objectives, scope and sponsor.
6. **What are your four objectives?** Assign all tasks to owners; track schedule/budget; support registrations/alerts; produce a closure report.
7. **What is inside MVP scope?** Events/venues, team task board, budget approvals, registrations/alerts and final report.
8. **What is excluded?** Advanced AI, hardware gate access and a multi-college marketplace.
9. **Why exclude features?** To prevent scope creep and protect time/cost/quality baselines.
10. **What is project lifecycle?** Initiate, plan, execute, monitor/control and close.
11. **Who approves a major scope change?** The project sponsor in the proposed governance model; the current demo simulates that decision locally.
12. **What is the project triangle?** Scope, time and cost are constrained, with quality affected by changes to them.
13. **What is a stakeholder matrix?** A categorization by influence and interest that guides communication and engagement.
14. **Project Manager vs Product Owner?** PM handles overall plan, coordination and reporting; PO prioritizes requirements and accepts increments.
15. **What is WBS?** Work Breakdown Structure: a deliverable-based hierarchy of manageable project packages.
16. **Which WBS packages do you show?** Initiation, planning, design, development, validation and closure.
17. **What is a Gantt chart?** A timeline that shows planned work duration and overlap.
18. **What is critical path?** The longest dependency path determining minimum project duration; delays on it delay the project, unless recovered.
19. **What's the critical path in this proposal?** Requirements → database design → backend APIs → integration → testing → deployment. The demo highlights this path as static baseline.
20. **How is Agile used?** Three short sprints: foundation, events/tasks and operational features, each with plan/build/test/demo/backlog refinement.
21. **What is risk management?** Identifying, analyzing, assigning, responding to and reviewing uncertainties that affect project objectives.
22. **Difference between risk avoidance, mitigation and transfer?** Avoid eliminates the exposure; mitigate reduces likelihood/impact; transfer shares financial/operational consequences with another party.
23. **Give a high risk from your plan.** Scope creep, treated by freezing MVP and formal change-control approval.
24. **What is SPI?** Schedule Performance Index = EV/PV, earned value divided by planned value; target >= 0.95 in the PPT.
25. **What is CPI?** Cost Performance Index = EV/AC, earned value divided by actual cost; target >= 0.95 in the PPT.
26. **What are the other quality targets?** Open critical defects = 0; sprint completion = accepted/planned >= 85%.
27. **How do data updates work?** JavaScript edits arrays/objects and persists them as JSON using browser Local Storage. All pages share the same storage origin.
28. **Why not call Local Storage a database?** It is browser-specific client storage; it does not support authenticated multi-user access, central backup or secure server controls.
29. **How does the website support different pages?** Ten distinct `.html` pages load shared CSS/JS; `body[data-page]` selects the page renderer. These are not React routes.
30. **What's next for production?** React/Vite frontend, Express REST APIs, PostgreSQL with Prisma, JWT plus server-enforced roles, automated alerts and Vercel/Render deployment, followed by tests and sponsor sign-off.

## Basic technical walkthrough

- `index.html`, `events.html`, etc.: Separate entry pages with the shared navbar and the appropriate `data-page` attribute.
- `styles.css`: Layout, sidebar, event visuals, dashboard cards, grids, Gantt styling, responsive breakpoints and print styles.
- `app.js`: Seed data, shared application state, form handling, CRUD actions, navigation-specific rendering, computed analytics and `localStorage` persistence.
- `assets/`: Festival PPT-derived illustration, compressed as WebP, and an SVG logo.
- `localStorage` key: `festpilot_aurora_demo_v2`. `JSON.stringify` writes application state and `JSON.parse` restores it.
- Event relationships: `eventId` points to an event in task and registration records.

## Do not claim

- That the live app uses React, Node.js, Express, PostgreSQL, Prisma or JWT. Those are **proposed**, not present.
- That someone is authenticated as a sponsor to approve funds. Approvals currently change local demo status only.
- That the sample numbers are actual fest budgets, approvals, registrations or measured project progress.
- That the app is deployed until the actual Vercel link loads and has been tested.

## What if asked why the PPT tech stack differs?

> This is the rapid interactive MVP for validating user workflows and project-management concepts. The slide-14 technology stack describes the intended secure full product. A real collaborative version needs an API, database and authorization layer. A static prototype is easier to demonstrate while we validate the requirements; I would migrate to the proposed stack in the next phase.

## Core terms to memorize

- **MVP** — Minimum Viable Product.
- **WBS** — Work Breakdown Structure.
- **PMIS** — Project Management Information System.
- **SPI** — Schedule Performance Index.
- **CPI** — Cost Performance Index.
- **EV** — Earned Value.
- **PV** — Planned Value.
- **AC** — Actual Cost.
- **QA** — Quality Assurance, improving process.
- **QC** — Quality Control, evaluating product.
- **JWT** — JSON Web Token, a proposed future authentication mechanism.

