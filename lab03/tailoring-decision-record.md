# TDR-01 · Life cycle and methodology for the Realtime Quiz project

**Status:** proposed · 2026-11-05 · to be decided by the Head of the IT department (sponsor), with recommendation from the supervising lecturer (project manager)

## Context

The Realtime Quiz project is delivered by four students working across backend, real-time, frontend, and QA/DevOps responsibilities, with the supervising lecturer acting as project manager. The project runs for 14 weeks from 2026-09-29, with a charter effort allocation of 490 person-hours and a cash cap of $200. The MoSCoW feature estimates total 504 hours, so the 14-hour difference must be reconciled in the week-3 plan rather than silently treated as available capacity. The sponsor requires a scope, requirements, risk, schedule, and quality baseline by week 3, a working MVP demonstration in week 7, and a pilot with 50 students in week 14. The MVP has eight Must features, while Should and Could features may be reordered or deferred; therefore, the core scope is reasonably defined but some details can change. Technical uncertainty is significant because campus proxy rules may block WebSockets, answer submission can race with question closure, client clocks may drift, and framework compatibility needs testing. The team has no recorded prior agile experience, so it needs clear planning and sponsor controls as well as short feedback cycles.

## Options considered

1. **Waterfall — 2.65:** Strong governance and upfront control, but delays working software and discovers real-time technical risks too late.
2. **Pure Scrum — 2.90:** Supports feedback and adaptation, but does not adequately protect the required week-3 baseline, fixed milestones, and sponsor approval controls for a team with no recorded Scrum experience.
3. **Hybrid — 4.00:** Combines a predictive week-3 baseline and sponsor phase gates with four two-week delivery sprints to test technical risks and refine lower-priority work.

Scores use the Task 1 weights: requirements stability 25, technical uncertainty 25, team agile experience 20, governance constraints 20, and early delivery/feedback 10. The weighted ranking is stable under the three sensitivity tests recorded in `approach-comparison.md`.

## Decision

Choose the **hybrid life cycle**. First, predictive planning protects the charter's fixed week-3 baseline, week-7 MVP, week-14 pilot, $200 cash cap, and sponsor change-control authority. Second, four short sprints expose WebSocket, timing, and integration problems early enough to respond before the final hardening and pilot-readiness work.

## Consequences

### Positive

- The Must-feature scope, schedule, effort estimate, risk approach, and cash limit are baselined before implementation, giving the sponsor a clear control point.
- Sprint reviews provide working increments and feedback while there is still time to change the backlog.
- Early integration and automated testing can reveal WebSocket, timing, and framework problems before the pilot.
- The week-13 readiness decision gives the sponsor measurable evidence before students take part in the pilot.

### Negative and mitigations

- Maintaining a baseline, gate evidence, backlog, and sprint records adds administration for a part-time team. **Mitigation:** use one shared status page and reuse sprint evidence in the gate packs; keep ceremonies time-boxed.
- The fixed gates could make the process behave like mini-waterfall and discourage reprioritisation. **Mitigation:** baseline the eight Must features and constraints, but allow the sponsor-approved backlog order for Should/Could work to change at each sprint review.
- The team has no recorded prior agile experience, so sprint planning and estimation may be inconsistent. **Mitigation:** use a short working agreement, a simple Definition of Done, lecturer coaching, and small tasks with estimates.
- Predictive estimates may become inaccurate when technical risks are tested. **Mitigation:** review estimates and the risk log at every sprint review; use formal change control only when a baseline or success criterion must change.

## Tailoring

| Keep from predictive | Keep from agile | Drop |
|----------------------|-----------------|------|
| **Week-3 scope and schedule baseline:** required by the charter and sponsor governance. | **Two-week sprints:** short feedback loops expose real-time technical risks early. | **Detailed upfront design for every screen:** UI details are uncertain and should be refined from working increments. |
| **WBS to level 2 and effort estimate:** gives the sponsor a manageable scope and resource baseline. | **Sprint planning and review:** the team selects work and demonstrates a working increment every two weeks. | **Fixed detailed assignment of all sprint work 14 weeks ahead:** it would prevent sensible reprioritisation after testing. |
| **Risk, quality, and change-control records:** protect the $200 cap, acceptance criteria, and fixed pilot date. | **Product backlog with MoSCoW priorities:** Must scope stays protected while Should/Could work can move. | **Daily long-form status reports and heavyweight sign-off for every task:** disproportionate for four part-time students. |
| **Four sponsor phase gates:** provide explicit continue, change, stop, or repeat decisions. | **Continuous integration and automated tests:** provide frequent evidence of build and integration quality. | **A separate Scrum Master role and extensive ceremony documentation:** the small team and lecturer can coordinate with a lightweight working agreement. |

## Phase gates

The sponsor is the decision maker at all four gates. The project manager prepares the evidence, recommends an outcome, and records the decision. Dates use the project calendar beginning 2026-09-29.

| Gate | Week and date | Evidence required | Decision maker | Possible outcomes |
|------|---------------|-------------------|----------------|-------------------|
| G1 — Plan approval | Week 3 · 2026-10-19 | 1. Approved scope statement and level-2 WBS covering all eight Must features. 2. Baselined 14-week schedule and an effort reconciliation showing how the 504-hour feature estimate fits the 490-person-hour charter allocation (or a sponsor-approved adjustment). 3. Risk, quality, and budget baseline showing cash spend at or below $200. | Head of the IT department (sponsor) | continue / continue with changes / stop / repeat |
| G2 — MVP checkpoint | Week 7 · 2026-11-16 | 1. Live demonstration passes all eight Must-feature acceptance checks. 2. Automated test report and CI result show no failing release-blocking tests. 3. Updated forecast shows a credible path to the 50-student pilot within the $200 cap. | Head of the IT department (sponsor) | continue / continue with changes / stop / repeat |
| G3 — Pilot-readiness | Week 13 · 2026-12-28 | 1. Load test passes with 100 simulated students and broadcast latency is at most 500 ms at p95. 2. Server-authoritative timer test shows client drift below 200 ms. 3. Runbook, data approval, and defect report confirm zero unresolved blocking defects. | Head of the IT department (sponsor) | continue / continue with changes / stop / repeat |
| G4 — Pilot and closure | Week 14 · 2027-01-04 | 1. Pilot attendance record confirms 50 students participated. 2. Pilot results show p95 broadcast latency at or below 500 ms and no unresolved blocking defects at pilot start. 3. Handover pack, lessons learned, and operational acceptance are recorded. | Head of the IT department (sponsor) | continue / continue with changes / stop / repeat |
