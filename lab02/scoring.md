# Weighted scoring · Build, Buy or Hybrid · Realtime Quiz pilot

Graded matrix: [`scoring.csv`](scoring.csv). Sources: charter (`../lab01/project-charter.md`), [`constraints.md`](constraints.md), [`moscow.md`](moscow.md), [`features.csv`](features.csv).

## 1. Weights (agreed 2026-10-27, before scoring)

Weights (agreed 2026-10-27, before any option was scored): **learning 30, cost 20, time 35, fit 15. Sum = 30 + 20 + 35 + 15 = 100.**

| Criterion | Weight | Why this weight |
|---|---:|---|
| Learning value for the capstone | 30 | The project is a Software Engineering capstone, so the team must actually design and code the system, but learning comes second to delivering the pilot. |
| Cost within the 200 USD cash budget | 20 | Cash is a fixed side of the triangle (200 USD cap, sponsor approval needed to exceed it), but the amounts are small, so cost gets less weight than time or learning. |
| Time to the week-14 pilot | 35 | Time is the **driver** in `constraints.md`: the week-7 MVP and week-14 pilot dates are fixed and missing them fails the project. That makes it the heaviest weight. |
| Fit to the 47 functional requirements | 15 | Scope **flexes** (Should + Could = 192 h can be deferred, `moscow.md`), so a partial fit can be handled through prioritisation. That makes it the lightest weight. |

Weight check: `=SUM(B2:B5)` = 30 + 20 + 35 + 15 = **100**.

## 2. Options

| Option | Description |
|---|---|
| **Build** | The Software Engineering capstone as planned: the four-student team builds the whole platform (Spring Boot + WebSocket, authoring, live sessions, scoring, leaderboard, analytics, export) and hosts it on one server instance. Cash: hosting 4 × 25 USD + domain 15 USD. |
| **Buy** | A hosted quiz service, **Kahoot! EDU Standard** (higher-education plan). Listed at about **15 USD per host per month, billed annually** (12 months minimum, so it costs 180 USD a year for one host licence, with no 4-month option). Students join free with a game PIN and nickname, and a session easily holds 50 students. The team configures the product and writes no platform code. |
| **Hybrid** | Buy the live-session engine (Kahoot! EDU Standard, same 180 USD licence) and build only **authoring, analytics and export**. The team's web app creates quizzes and writes them out in Kahoot!'s `.xlsx` import template. After each session, it reads the Kahoot! `.xlsx` report and produces analytics and CSV/PDF exports. The app needs its own hosting (4 × 25 USD). |

> Price note: the Kahoot! figure comes from the vendor's published higher-education pricing as checked on 2026-10-27. It must be re-checked (and a quote obtained) before any purchase, as the charter requires for all prices.

## 3. Scores and evidence (1 = poor, 5 = excellent)

| Criterion | Weight | Build | Buy | Hybrid |
|---|---:|---:|---:|---:|
| Learning value | 30 | 5 | 1 | 3 |
| Cost within 200 USD | 20 | 4 | 2 | 1 |
| Time to week-14 pilot | 35 | 2 | 5 | 4 |
| Fit to requirements | 15 | 5 | 3 | 4 |
| **Weighted score** | | **375** | **290** | **310** |
| **Percent of 500** | | **75 %** | **58 %** | **62 %** |

### Evidence, one line per score

**Learning value (weight 30)**
- Build scores 5 on learning: the team codes all 17 features (504 h), including the hard parts (WebSocket F05, server-authoritative timer F07, concurrent sessions F08), which are exactly what the capstone assesses.
- Buy scores 1 on learning: the team writes no code and only configures Kahoot!, so none of the capstone's design, coding or testing outcomes are exercised.
- Hybrid scores 3 on learning: the team still builds authoring F01 (44 h), auth F06 (44 h), analytics F10 (30 h) and export F11 (24 h) = 142 h, but skips the real-time core (F02 + F05 + F07 = 128 h), which is the most valuable learning.

**Cost within the 200 USD cash budget (weight 20)**
- Build scores 4 on cost: hosting 4 × 25 USD + domain 15 USD = 115 USD, 57.5 % of the cash budget, leaving 85 USD (including the 25 USD reserve). Not 5, because recurring hosting is still a real cost.
- Buy scores 2 on cost: 15 USD/month × 12 months (annual billing only) = 180 USD, 90 % of the cash budget. That leaves 20 USD, below the 25 USD reserve, and a second instructor licence (360 USD, 180 %) would break the cap.
- Hybrid scores 1 on cost: Kahoot! 180 USD + hosting 4 × 25 USD = 280 USD, 140 % of the cash budget. It cannot go ahead without written sponsor approval.

**Time to the week-14 pilot (weight 35)**
- Build scores 2 on time: the 504 h feature estimate exceeds the 490 h capacity by 14 h (103 %), and the WebSocket campus-proxy risk and the week-13 100-student load test are both on the critical path, so there is no slack.
- Buy scores 5 on time: the service works on day one, so a 50-student pilot could run in week 1 with only quiz entry and account set-up left to do.
- Hybrid scores 4 on time: 142 h of build is 29 % of the 490 h capacity, which leaves a large buffer. It loses a point because Kahoot! has no public hosting API, so integration relies on its `.xlsx` import/report formats, which can change.

**Fit to the 47 functional requirements (weight 15)**
- Build scores 5 on fit: the system is designed against the requirements, and every feature F01–F16 traces to FR ids in `features.csv`, so any gap can be closed in our own code.
- Buy scores 3 on fit: Kahoot! covers 7 of 8 Must features. It misses F06 (players join anonymously by PIN, with no instructor/student accounts we control), exports only `.xlsx` (no Khmer-safe PDF, F11), and we cannot measure the 500 ms p95 latency or 200 ms drift NFRs on servers we do not own.
- Hybrid scores 4 on fit: Kahoot! covers the real-time Musts, and our own build adds F06 auth, F10 analytics and F11 CSV/PDF export. It loses a point because the latency/drift NFRs still cannot be measured, and the hand-over between the two parts is by file, not live.

## 4. Formulas (as written in `scoring.csv`) and hand check

| Cell | Formula (text in CSV) | Hand calculation | Result |
|---|---|---|---:|
| B6 | `=SUM(B2:B5)` | 30 + 20 + 35 + 15 | **100** |
| C7 | `=SUMPRODUCT($B$2:$B$5,C2:C5)` | 30×5 + 20×4 + 35×2 + 15×5 = 150 + 80 + 70 + 75 | **375** |
| D7 | `=SUMPRODUCT($B$2:$B$5,D2:D5)` | 30×1 + 20×2 + 35×5 + 15×3 = 30 + 40 + 175 + 45 | **290** |
| E7 | `=SUMPRODUCT($B$2:$B$5,E2:E5)` | 30×3 + 20×1 + 35×4 + 15×4 = 90 + 20 + 140 + 60 | **310** |
| C8 | `=C7/(5*$B$6)` | 375 / (5 × 100) = 375 / 500 | **75 %** |
| D8 | `=D7/(5*$B$6)` | 290 / 500 | **58 %** |
| E8 | `=E7/(5*$B$6)` | 310 / 500 | **62 %** |

**Result: Build wins (375, 75 %)**, ahead of Hybrid (310, 62 %) by 65 points and Buy (290, 58 %) by 85 points.

## 5. Sensitivity check

Move 10 points of weight from the heaviest criterion (**time 35 → 25**) to the lightest (**fit 15 → 25**). New weights: learning 30, cost 20, time 25, fit 25. Sum = 100.

- Build = 30×5 + 20×4 + 25×2 + 25×5 = 150 + 80 + 50 + 125 = **405** (81 %)
- Buy = 30×1 + 20×2 + 25×5 + 25×3 = 30 + 40 + 125 + 75 = **270** (54 %)
- Hybrid = 30×3 + 20×1 + 25×4 + 25×4 = 90 + 20 + 100 + 100 = **310** (62 %)

Sensitivity (time 25, fit 25): Build 405, Buy 270, Hybrid 310. **Winner unchanged: Build**, and its lead over Hybrid grows from 65 to 95 points, because the shift takes weight away from Build's weakest criterion (time) and gives it to one of its strongest (fit).

Extra check in the opposite direction: moving 10 points from learning to time (learning 20, time 45) gives Build 20×5 + 20×4 + 45×2 + 15×5 = 345, Buy 20×1 + 20×2 + 45×5 + 15×3 = 330, and Hybrid 20×3 + 20×1 + 45×4 + 15×4 = 320. Build still wins, but only by 15 points. **The decision is most sensitive to the weight on time.** Build stays the right choice only if the schedule risk is actively managed: defer the 106 h of Could features, and test WebSocket through the campus proxy in the first weeks.
