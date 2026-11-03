# DR-01 · Open-day demo scope, week 10

| Field | Value |
|---|---|
| Record ID | DR-01 |
| Title | Open-day demo scope, week 10 |
| Date | 2026-10-24 |
| Status | Approved |
| Requested by | Head of IT (Sponsor, S01) |
| Decided by | Project Manager (S02) and Head of IT (S01) |

---

## 1. Context

At the conclusion of Sprint 2 (end of Week 4), the Sponsor (Head of IT, S01) requested that all Should features be completed and demonstrable by Week 10 for a faculty-wide open day, while maintaining the committed 50-student pilot at Week 14.

### Fixed constraints and facts
- **C-01 (Time):** Total duration is 14 weeks from 2026-09-29. The Week 14 pilot (2027-01-05) remains fixed. Adding an intermediate public demonstration in Week 10 introduces a new schedule gate.
- **C-02 (Resources & Cost):** Team capacity is strictly 4 students × 10 h/week = 40 h/week (240 person-hours available across Weeks 5–10). No external hiring or paid overtime is permitted.
- **C-03 (Cash Budget):** Total cash expenditure is capped at 200 USD ($0 available for outside contracting).
- **C-04 (Architecture):** Single-instance Ubuntu Linux VPS deployment.
- **C-05 (Security):** Zero credentials committed to Git repositories.
- **C-06 (Quality Floor):** Broadcast latency ≤ 500 ms at p95, automated test line coverage ≥ 80%, green CI on all merges, and client clock drift < 200 ms.

### Empirical delivery data (end of Week 4)
- Sprints 1 and 2 delivered 18 and 21 story points (average velocity: 19.5 points/sprint).
- Of the 300 total Must hours, 148 hours are completed; 152 hours of Must work remain.
- The 5 planned Should features (F09 Responsive Design 20 h, F10 Analytics 30 h, F11 CSV/PDF Export 24 h, F12 Real-time Notifications 12 h, F13 Multimedia 24 h) total 110 hours.
- Total effort required for Must remaining + all Should = 152 h + 110 h = 262 hours.
- Available capacity (Weeks 5–10) = 240 hours.
- This creates an unbuffered deficit of 22 hours (0.55 weeks) with zero contingency. When preserving the project's standard 56-hour contingency buffer (10% reserve), the deficit is 78 hours (1.95 weeks ≈ 2 weeks). Delivering the entire Should scope by Week 10 is mathematically unachievable under C-02.

---

## 2. Options considered

| Option | Time | Cost (Hours & Cash) | Quality Impact | Assessment |
|---|---|---|---|---|
| **Option 0: Sponsor request as stated** (All Must + all 110 h Should by W10) | W10 demo; W14 pilot | 262 h required vs. 240 h capacity (shortfall: 22 h pure, 78 h buffered); $0 cash | Severe violation of C-06 quality floor; testing and integration cut to rush features | **Rejected:** Exceeds capacity C-02, exhausts contingency, risks catastrophic failure during live open day. |
| **Option 1: Counter-proposal 1** (Must complete + F09 Responsive [20 h] + F10 Analytics [30 h] by W10; F11, F12, F13 deferred to W14) | W10 demo ready; W14 pilot intact | 202 h required (152 h Must + 50 h Should); leaves 38 h contingency buffer (15.8%); $0 cash | Meets all C-06 quality criteria (≥ 80% coverage, p95 latency ≤ 500 ms); clean mobile and dashboard UX | **Accepted:** Delivers high visual impact on open day while preserving adequate buffer for reliability. |
| **Option 2: Counter-proposal 2** (Must complete + Mocked Analytics Demo stub [8 h] by W10; all real Should deferred to W14) | W10 demo ready; W14 pilot intact | 160 h required (152 h Must + 8 h mock); leaves 80 h contingency buffer (33.3%); $0 cash | Protects core stability, but demo analytics are non-functional mock data | **Rejected in favor of Option 1:** Viable fallback, but fails to provide the genuine interactive analytics requested by sponsor. |

---

## 3. Decision

Adopt **Counter-Proposal 1 (Option 1)**:

1. **Week 10 Open Day Demo milestone scope:**
   - Complete remaining Must features F01–F08 (152 h).
   - Accelerate **F09 Responsive design (20 h)** and **F10 Analytics and reporting (30 h)** into the Week 10 release.
   - Total planned effort: 202 person-hours across Weeks 5–10.
   - Retain a 38-hour (15.8%) contingency buffer against the 240-hour capacity ceiling.

2. **Scope deferred to Week 14 Pilot milestone:**
   - **F11 Export results to CSV and PDF (24 h)**
   - **F12 Real-time notifications (12 h)**
   - **F13 Multimedia in questions (24 h)**

3. **Scope classified as Won't before Week 11:**
   - All Could features—**F14 Chat during sessions (40 h)**, **F15 Anonymous joining with nickname (12 h)**, **F16 Shared question bank (30 h)**, and **F17 Admin role (12 h)**—are frozen and categorized as *Won't prior to Week 11*.

---

## 4. Consequences

### Positive consequences
- The department obtains a compelling, fully responsive platform with live visual analytics to demonstrate to visitors at the Week 10 open day.
- Core quiz participation (F02) and WebSocket synchronization (F05) are protected by a dedicated 38-hour quality and stabilization buffer.
- No increase in cash budget (C-03 remains strictly preserved at 200 USD).
- Fixed team capacity C-02 (40 h/week) is respected without developer burnout or timetable collisions.

### Negative consequences and trade-offs
- Features F11 (CSV/PDF export), F12 (notifications), and F13 (multimedia) are unavailable during the Week 10 open day. Presenters must explain that export reports and multimedia questions are scheduled for the subsequent semester pilot release.
- Work on Could features is completely halted until after the Week 10 demo.

### Schedule baseline changes
- A new intermediate milestone gate **"Open Day Demo"** is added at Week 10 (2026-12-08) in the project schedule baseline.
- Sprint 3 (Weeks 5–6) focuses on finishing F05 (WebSocket updates) and starting F09 (Responsive design).
- Sprint 4 (Weeks 7–8) focuses on finishing Must features and implementing F10 (Analytics).
- Sprint 5 (Weeks 9–10) focuses on integration, cross-device testing, buffer absorption, and open day rehearsals.

### Risk management updates
- **Risk logged:** **R-10** (*Demo on newly integrated analytics and responsive layout encounters unexpected device resolution glitches or performance hiccups during open day*).
  - *Probability:* Medium (3/5).
  - *Impact:* Medium (3/5).
  - *Mitigation:* Conduct a full dry-run demo during Sprint 4 review (Week 8) using standard faculty tablets and laptops; enforce 38 hours of reserved buffer for cross-browser testing and bug fixes; prepare pre-seeded sample quiz sessions as offline fallback.

---

## 5. Approvals

| Name | Role / Stakeholder ID | Decision | Date |
|---|---|---|---|
| **Head of IT** | Project Sponsor (S01) | Approved | 2026-10-24 |
| **PM (Supervising Lecturer)** | Project Manager (S02) | Approved | 2026-10-24 |
| **Student Team Lead** | Engineering Team Lead (S03) | Acknowledged & Committed | 2026-10-24 |
| **Capstone Coordinator** | Academic Evaluator (S08) | Noted in Baseline | 2026-10-24 |
