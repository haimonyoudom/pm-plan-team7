# Project charter: Realtime Quiz platform

| Field | Value |
|---|---|
| Version | 1.0 (draft for sponsor approval) |
| Date | 2026-09-29 |
| Sponsor | Head of the IT department |
| Project manager | Supervising lecturer |
| Team | Four students: backend, real-time, frontend, QA/DevOps |
| Planned duration | 14 weeks, starting 2026-09-29 |
| Business case | See [`business-case.md`](business-case.md) |

## 1. Purpose and justification

Lecturers need a way to run live multiple-choice quizzes and give students immediate feedback without carrying the full burden of manual marking and delayed result sharing. The Realtime Quiz platform will let instructors create quizzes, host timed sessions, and show scores and leaderboards to students in real time. The project will deliver an MVP demonstration in week 7 and a pilot with 50 students in week 14, within the $200 cash cap. The investment recommendation, assumptions, alternatives, and payback calculations are documented in [`business-case.md`](business-case.md); the recommendation is to build the platform if the week-7 MVP gate is passed.

## 2. Objectives and success criteria

| # | Objective (what will be true) | Success criterion (number + week) |
|---|---|---|
| O1 | Deliver the MVP's required quiz-authoring and live-session features. | By week 7, demonstrate all Must features: quiz creation, timed multiple-choice questions, authentication/roles, live participation, instant scoring/feedback, leaderboard, WebSocket updates, and multiple concurrent sessions. |
| O2 | Run a pilot that validates the platform with students. | By week 14, complete one pilot with 50 students and zero unresolved blocking defects at pilot start. |
| O3 | Keep real-time broadcast performance within the target. | By week 14, measured broadcast latency is at most 500 ms at the 95th percentile during the agreed pilot/load test. |
| O4 | Verify the planned capacity and timer behaviour. | By week 13, pass a load test with 100 simulated students and verify server-authoritative question timing with client drift below 200 ms. |
| O5 | Maintain test and accessibility quality. | By week 14, achieve at least 80% line coverage, green CI on every merge, keyboard access, WCAG AA contrast checks, and support for the last two versions of major browsers. |

## 3. High-level scope

### In scope

- Multiple-choice quiz authoring and editing deliverables.
- Timed live quiz-session and question-control deliverables.
- Student joining by six-character session code.
- Real-time answer feedback, score calculation, and leaderboard views.
- Authentication and role-based access for instructors and students.
- Concurrent live-session support for the stated single-instance target.
- Analytics and result-export deliverables where time permits after the MVP.
- Responsive web interface and real-time notifications where time permits.

### Out of scope

- Native Android or iOS mobile applications.
- Free-text, essay, or question types other than multiple choice.
- Video-conferencing functionality.
- Learning Management System (LMS) integration.
- Multi-node or horizontally scaled deployment.
- Chat, shared question banks, and a full administration screen unless formally approved as stretch work.

## 4. Milestones

| Week | Milestone | Ends process group |
|---:|---|---|
| 1 | Charter approved, sponsor and team confirmed, initial stakeholder list accepted | Initiating |
| 3 | Scope, requirements, risk list, schedule, and quality approach baselined | Planning |
| 5 | Account/security and quiz-authoring increment reviewed | Executing |
| 7 | MVP demonstration covering all Must features | Executing |
| 10 | Analytics/export and selected Should features reviewed; updated risk and test plan approved | Executing |
| 13 | Pilot-readiness gate: 100-student load test, data approval, runbook, and defect review | Monitoring and controlling |
| 14 | Pilot with 50 students, handover, lessons learned, and formal closure | Closing |

## 5. Budget summary

### Effort

- Students: 4 × 14 weeks × 8 hours/week = **448 person-hours**
- Project manager: 14 weeks × 3 hours/week = **42 person-hours**
- Total planned effort: 448 + 42 = **490 person-hours**
- Notional comparison value: 490 hours × $10/hour = **$4,900** (economic value of effort, not cash paid to students)

### Cash

- Hosting: 4 months × $25/month = **$100**
- Domain: 1 × $15 = **$15** (estimate)
- Optional paid tools: 1 allowance × $60 = **$60** (estimate; use free tools where possible)
- Cash lines before reserve: $100 + $15 + $60 = **$175**
- Reserve: $25; $25 ÷ $175 = **14.3% of pre-reserve cash lines**
- Total cash cap: $175 + $25 = **$200**

The project must not exceed the $200 cash cap without written sponsor approval. The four-month hosting estimate is a planning assumption; actual billing and domain/tool prices must be checked before purchase.

## 6. Assumptions

- The four student team members can each contribute about 8 hours per week for 14 weeks.
- The supervising lecturer can contribute about 3 hours per week and attend decision gates.
- The department provides access to the required test environment and can arrange a 50-student pilot.
- A single application instance is acceptable for the semester pilot.
- The campus network permits WebSocket traffic; if the proxy blocks it, SockJS fallback will be evaluated.
- The SaaS cost in the business case is an assumption of $15 per lecturer per month, not a verified vendor quote.

## 7. Constraints

- The project lasts 14 weeks, starting 2026-09-29.
- The MVP demo must happen in week 7; the 50-student pilot must happen in week 14.
- Cash spending is capped at $200 unless the sponsor approves a change.
- The team consists of four students with limited part-time effort.
- The product is a web platform using one server instance; native mobile apps and multi-node scaling are excluded.
- No secrets may be committed to the repository.

## 8. High-level risks

- Campus proxy rules may block WebSocket traffic; test early and evaluate SockJS fallback.
- Late answers may race with question closure, and client clocks may drift; use server-authoritative timing and automated tests.
- Newer Spring Boot/Spring Security versions may differ from common tutorials; reserve time for compatibility tests.
- PDF export may render Khmer names incorrectly; test representative Khmer names before promising PDF export.
- Stretch features may expand the MVP; protect Must-feature scope through change control.

## 9. Project manager authority

The project manager may coordinate the team, assign and sequence work, approve day-to-day technical decisions, maintain the risk and issue logs, and re-plan within the agreed 490 person-hours, 14-week duration, scope, and $200 cash cap. The PM may defer Could features to protect the MVP and may approve corrective actions that do not change the baselines. Written sponsor approval is required to add or remove major scope, move the week-7 MVP or week-14 pilot, exceed the cash cap or reserve, or change the agreed success criteria. The sponsor should respond to a submitted change request within five working days.

## 10. Approval

| Role | Name/signature | Date |
|---|---|---|
| Sponsor — Head of the IT department | ______________________________ | __________ |
| Project manager — supervising lecturer | ______________________________ | __________ | Tong Sreng
