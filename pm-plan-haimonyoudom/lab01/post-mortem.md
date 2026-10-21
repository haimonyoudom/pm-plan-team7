# Post-mortem: CampusPay wallet (fictional case supplied in Lab-01)

## 1. Timeline and sources

| # | When | Event | Source |
|---:|---|---|---|
| 1 | Project start | The university asks its IT unit to build a cashless payment app for the canteen and library fines in one semester. | Fictional case from Lab-01 |
| 2 | Initiation | The head of finance sponsors the project by email but does not attend reviews. | Fictional case from Lab-01 |
| 3 | Early planning | The lead developer acts as both PM and coder; success is defined only as “launch in September.” | Fictional case from Lab-01 |
| 4 | Requirements gathering | A survey expands scope from canteen payments to bus tickets and parking. | Fictional case from Lab-01 |
| 5 | Before launch | The team does not test with real card terminals before launch day. | Fictional case from Lab-01 |
| 6 | Launch day | Terminals reject 40% of payments and the canteen queue doubles. | Fictional case from Lab-01 |
| 7 | Three days after launch | The app is withdrawn. | Fictional case from Lab-01 |
| 8 | Five months later | The app relaunches for canteen payments only. | Fictional case from Lab-01 |

## 2. Classification and organisation

The effort was a **project** because it had a temporary time window and was intended to create a new payment app. The later narrowed relaunch could be treated as a corrective follow-up project if separately authorised. The case does not establish that it was a programme because no coordinated set of related projects with shared benefits is described.

The lead developer worked in a role-conflicted structure, acting as both project manager and implementer. The case does not specify the formal organisational structure or a PMO, so those details cannot be confirmed. A nominal sponsor existed, but the sponsor did not participate in reviews. There is no evidence of a signed project charter, agreed authority limits, or a PMO.

## 3. Success criteria

The stated success criterion was “launch in September.” It was not a sufficient measurable definition of success because it did not define payment acceptance rate, transaction accuracy, response time, user impact, reliability, security, or operational readiness.

Missing criteria included:
- A target for successful transactions on the actual card terminals.
- End-to-end test pass rates and acceptable defect thresholds.
- A pilot or staged rollout with real users and a rollback plan.
- Measurable queue time and service availability targets.
- Named operational ownership, support procedures, and acceptance sign-off.

The project ignored wider success dimensions: user experience (the canteen queue doubled), benefits (cashless payments were not reliably delivered), operations (real terminal compatibility was untested), and team capacity (the lead developer had two conflicting responsibilities).

## 4. Process groups and knowledge areas

| Process group | What went wrong or was skipped |
|---|---|
| Initiating | Sponsorship was nominal and no effective charter or decision-making commitment is evidenced, so authority and success were unclear. |
| Planning | Scope expanded to bus tickets and parking without evidence of approved change control, and measurable acceptance criteria were missing. |
| Executing | The team built the application without validating it against real card terminals before launch. |
| Monitoring and controlling | Reviews did not expose scope growth or readiness gaps; the sponsor's absence weakened escalation and corrective action. |
| Closing | The initial launch was withdrawn after three days, indicating that acceptance and operational handover were not successful; a structured lessons-learned process is not described. |

Three knowledge areas most responsible:

1. **Scope management:** bus tickets and parking were added after the initial canteen/library scope, without a stated approval gate.
2. **Risk management:** compatibility with real payment terminals was a foreseeable risk but was not tested before launch.
3. **Stakeholder management:** the sponsor did not attend reviews, and the needs of canteen users and operations were not adequately validated.

Schedule and quality management also contributed: “launch in September” encouraged a date-focused view without measurable product quality.

## 5. Ethics

**Decision examined:** proceeding to launch without testing the app with real card terminals. This decision did not adequately meet **responsibility**, because the team should have tested a critical payment path; **respect**, because it exposed canteen users to disruption; **fairness**, because users bore the cost of an unready system; or **honesty**, if launch readiness was presented without clear evidence of terminal compatibility. The case does not say what was communicated to users, so any claim of deliberate deception would be unsupported.

## 6. What our project will do differently

| # | Commitment (We will ...) | Measured by | By week | Charter line |
|---:|---|---|---:|---|
| 1 | We will keep a signed charter with a named sponsor who attends the key decision gates. | Sponsor signature and recorded gate decisions | 1 | Charter approval; section 10 |
| 2 | We will protect the Must-feature MVP and route major scope changes through sponsor approval. | Approved scope baseline and change log; no unapproved scope additions | 3 onward | Section 3 scope; section 9 authority |
| 3 | We will test real-time broadcast performance and timer behaviour before the pilot. | Broadcast latency ≤500 ms at p95 and client timer drift <200 ms in test evidence | 13 | O3 and O4 |
| 4 | We will run a load test and resolve blocking defects before inviting pilot students. | 100 simulated students; test report reviewed; zero unresolved blocking defects at pilot start | 13 | O2 and O4; week-13 pilot-readiness gate |
| 5 | We will obtain student-data approval and hand over an operations runbook before go-live. | Written data approval, deployment/backup runbook, and named operations owner | 13 | Assumptions and constraints; week-13 gate; week-14 handover |
