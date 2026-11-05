# Approach comparison · Realtime Quiz

Sources: [project profile](project-profile.md) (Task 1, profile 3.05 = hybrid band), [charter](../lab01/project-charter.md), [MoSCoW list](../lab02/moscow.md)

| Approach | Requirements | Sponsor control | First quiz | Two main risks | Fit |
|------------|--------------|-----------------|-----------:|-----------------|------|
| Waterfall | All 17 features specified and signed off up front (weeks 1–3); later changes go through formal change requests against the baseline. | Sponsor approves the requirements, design and test phase gates; progress is reported as % of plan complete, budget tracked against the $200 baseline. | week 11 | 1. WebSocket blocking, timing races and clock drift are only discovered at integration (weeks 10–11), too late to fix before the pilot. 2. The UI is not specified in the charter, so the signed-off spec is guessed and the week-7 MVP demo shows documents, not software. | Low: strong on governance (weight 20) but weak on technical uncertainty (weight 25) and early feedback; contradicts the week-7 MVP demo. |
| Pure Scrum | Product backlog reordered every 2-week sprint; no scope baseline, Must features are just the top of the backlog. | Sponsor sees a sprint review every 2 weeks but has no gate to approve a baseline, stop or re-plan; budget and date tracked only through velocity. | week 4 | 1. A first-time agile team (no recorded Scrum experience) drifts without a plan, estimates and ceremonies degrade. 2. The fixed week-7 and week-14 dates and the week-3 baseline required by the charter are not protected. | Medium: strong on technical uncertainty and feedback, weak on governance and team experience (together weight 40). |
| Hybrid | Must features and the 504 h estimate baselined in the week-3 plan (predictive); Should/Could features ordered in a backlog and refined each sprint (adaptive). | Sponsor approves the plan at the week-3 gate, the MVP at the week-7 gate and go/no-go before the week-14 pilot; attends sprint reviews in between; major changes go through change control. | week 5 | 1. Double overhead: the part-time team must maintain both the plan/gates and the Scrum events. 2. Gates and baseline harden into mini-waterfall, so the team resists re-ordering the backlog after a sprint review. | High: matches the 3.05 hybrid profile — sprints absorb technical risk, gates satisfy the charter's baseline and milestone constraints. |

Columns: how requirements are handled · how the sponsor controls the project (governance) · week in which the sponsor first plays a working quiz · two main risks · fit with the Task 1 profile

First-quiz weeks assume a 14-week project starting 2026-09-29: Waterfall finishes build and integration in week 11; Scrum starts sprint 1 in week 1, so the sprint-2 review is in week 4; Hybrid spends weeks 1–3 on the plan, so the first sprint review (sprint 1 = weeks 4–5) is in week 5.

## Weighted score (from approach-scoring.csv)

Fit score per criterion: 1 = poor, 5 = excellent. Weights reused from Task 1 (25 / 25 / 20 / 20 / 10 = 100).

| Criterion | Weight | Waterfall | Scrum | Hybrid |
|---|---:|---:|---:|---:|
| Requirements stability | 25 | 2 | 3 | 4 |
| Technical uncertainty | 25 | 1 | 5 | 4 |
| Team experience with agile | 20 | 4 | 1 | 3 |
| Contract and governance constraints | 20 | 5 | 1 | 5 |
| Need for early delivery and feedback | 10 | 1 | 5 | 4 |
| **Weighted score** | 100 | **2.65** | **2.90** | **4.00** |

Formula in the spreadsheet: `=SUMPRODUCT($B$2:$B$6,C$2:C$6)/100`, copied to D and E.

- Waterfall = (25·2 + 25·1 + 20·4 + 20·5 + 10·1) / 100 = 265 / 100 = **2.65**
- Scrum = (25·3 + 25·5 + 20·1 + 20·1 + 10·5) / 100 = 290 / 100 = **2.90**
- Hybrid = (25·4 + 25·4 + 20·3 + 20·5 + 10·4) / 100 = 400 / 100 = **4.00**

Waterfall 2.65 · Scrum 2.90 · Hybrid 4.00

## Sensitivity

- Test 1: team experience with agile (hardest to judge, since the charter records no experience either way) 20 → 30, governance 20 → 10: Waterfall 2.55 · Scrum 2.90 · Hybrid 3.80, so the ranking does not change and Hybrid stays first by 0.90.
- Test 2: early delivery 10 → 20, requirements stability 25 → 15: Waterfall 2.55 · Scrum 3.10 · Hybrid 4.00, so the ranking does not change, although Scrum moves 0.45 ahead of Waterfall.
- Test 3: technical uncertainty 25 → 35, governance 20 → 10: Waterfall 2.25 · Scrum 3.30 · Hybrid 3.90, so the ranking does not change and Scrum closes to within 0.60 of Hybrid.

The ranking Hybrid > Scrum > Waterfall is stable under all three ±10 weight shifts.

## Recommendation

**Hybrid (4.00)**: a predictive plan approved at the week-3 gate with the Must features baselined, then 2-week sprints with sponsor gates at the week-7 MVP demo and before the week-14 pilot. The runner-up is **Pure Scrum (2.90)**. We would choose Scrum instead only if the sponsor dropped the week-3 baseline and gate approvals from the charter and agreed to attend every sprint review as the governance mechanism.

