# Business case: live quizzes for the IT department

> **Pricing note:** The SaaS price below is the lab's permitted assumption of **$15 per lecturer per month**, not a verified vendor quote. Obtain a real education-price quote and check its data terms before purchasing. Figures are planning estimates, not guaranteed savings.

## 1. Problem

Lecturers who run quizzes may spend time marking responses and returning results after the session. Realtime Quiz could reduce manual marking time and provide immediate feedback, while giving the department a reusable software-engineering learning outcome and greater control over quiz data.

Assumptions used for comparison:

- Lecturers running quizzes: **10**
- Marking time per lecturer per week: **1 hour**
- Teaching weeks per year: **30**
- Notional value of one hour: **$10** (comparison value only; student effort is not a cash salary)
- Annual marking effort: 10 × 1 × 30 = **300 hours**
- Annual value of that effort: 300 × $10 = **$3,000**
- SaaS assumption: 10 lecturers × $15/month × 12 months = **$1,800/year**
- Build effort value: 490 person-hours × $10/hour = **$4,900 one-off**
- Build hosting: $25/month × 12 months = **$300/year** after the initial four-month project estimate.

## 2. Options

| Option | Description | One-off cost | Annual cost | Annual benefit |
|---|---|---:|---:|---:|
| A | Do nothing; continue existing quiz and marking methods | $0 | $0 | $0 incremental benefit |
| B | Buy an existing quiz SaaS; price is assumed at $15 per lecturer/month | $0 setup assumed | $1,800 | $3,000 marking-time value |
| C | Build Realtime Quiz using the charter budget | $4,900 effort value | $300 hosting | $3,000 marking-time value + $1,800 avoided SaaS fee |

The charter's **$200 cash cap** is separate from the economic value of team effort. Option C has a $200 planned project cash budget ($100 hosting during the four-month build, $15 domain, $60 tools allowance, and $25 reserve), while the comparison also records the $4,900 notional effort value. For annual operating comparisons, hosting is estimated at $300/year.

## 3. Comparison

Net annual benefit = annual benefit − annual cost. Payback = one-off cost ÷ net annual benefit when the net annual benefit is positive. For option B, no one-off cost is assumed, so payback is **0 years / not applicable** rather than a meaningful investment recovery period.

| Option | Net annual benefit | Payback (years) | Sensitivity with 6 lecturers |
|---|---:|---:|---:|
| A — Do nothing | $0 | Not applicable | $0 |
| B — Buy SaaS | $3,000 − $1,800 = **$1,200** | **0 / N/A** (no one-off setup cost assumed) | $1,800 benefit − $1,080 fee = **$720/year** |
| C — Build | $3,000 + $1,800 − $300 = **$4,500** | $4,900 ÷ $4,500 = **1.09 years** | $1,800 marking value + $1,080 avoided SaaS fee − $300 hosting = **$2,580/year**; $4,900 ÷ $2,580 = **1.90 years** |

The six-lecturer sensitivity case changes the number of lecturers from 10 to 6 while keeping the hours/week, teaching weeks, notional hourly value, hosting, and build effort constant. This is a simplified economic comparison; actual benefits depend on whether the platform really replaces manual marking and whether the department would otherwise pay for a SaaS.

## 4. Benefits not priced

- Students receive immediate feedback and can see the leaderboard during a session.
- The team gains practical experience in real-time software, testing, deployment, and project management.
- The department retains more control over its quiz data and can adapt the platform to its own needs.
- A self-hosted solution has no per-lecturer subscription limit, although it still has hosting and maintenance costs.
- The platform may support future teaching improvements if the pilot shows clear value.

## 5. Risks per option

### Option A — Do nothing

- Manual marking and delayed feedback continue.
- The department misses the opportunity to develop and evaluate a reusable tool.
- Different lecturers may continue using inconsistent quiz workflows.

### Option B — Buy SaaS

- The assumed price may be inaccurate; actual education pricing or feature limits may differ.
- Student-data storage, retention, or vendor terms may not meet department requirements.
- Internet access or vendor outages may interrupt live quizzes.
- Long-term subscription costs rise if more lecturers adopt the tool.

### Option C — Build Realtime Quiz

- Campus proxy rules may block WebSocket traffic; SockJS may be needed.
- Late answers and question closure may race, and client clocks may drift.
- Spring Boot/Spring Security version differences may consume schedule time.
- Khmer names may render incorrectly in PDF exports.
- Stretch features could expand the MVP and put week 7 at risk.

## 6. Recommendation and review gate

**Recommend option C (build Realtime Quiz), conditionally.** Under the stated assumptions, the net annual benefit is $4,500 and the notional effort-value payback is about 1.09 years; with only six lecturers, the simplified payback is about 1.90 years. This recommendation also values learning outcomes and data ownership that are not fully captured by the calculation.

**Review gate:** At the week-7 MVP demonstration, the sponsor should check whether all Must features work and whether the remaining schedule and risk are acceptable. If the MVP fails its acceptance criteria or the remaining work cannot realistically reach pilot readiness, the sponsor should consider option B for the next semester rather than allowing unapproved scope or cost growth. No SaaS purchase should be made until actual pricing and student-data terms have been checked.
