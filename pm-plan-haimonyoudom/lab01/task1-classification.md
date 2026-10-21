# Task 1: project, operation or programme?

| # | Initiative | Temporary? | Unique? | Coordinated? | Class | Justification |
|---:|---|:---:|:---:|:---:|---|---|
| 1 | Build the Realtime Quiz platform and pilot it with 50 students in week 14 | Yes | Yes | No | Project | It has a defined start and week-14 end, and produces a new quiz platform and pilot result. |
| 2 | Run the nightly backup of the gicitc.com PostgreSQL database | No | No | No | Operation | It repeats every night with the same purpose and has no planned end date. |
| 3 | Move the department's three web servers to a new Linode region before 15 December | Yes | Yes | No | Project | It is a one-time migration with a deadline and a changed hosting arrangement. |
| 4 | Answer helpdesk tickets within the 4-hour service level | No | No | No | Operation | Tickets are handled continuously under a recurring service-level target. |
| 5 | "Digital classroom": Realtime Quiz, LMS upgrade and lecture capture sharing one login and one grade export | Yes | Yes | Yes | Programme | The related projects must be coordinated to deliver shared login and grade-export benefits. |
| 6 | Apply the monthly security patches to the VPS | No | No | No | Operation | Patching recurs monthly as routine service maintenance without a defined final end. |
| 7 | Add multi-node scaling (RabbitMQ relay, Redis registry) to Realtime Quiz next semester | Yes | Yes | No | Project | If separately authorised, funded, and completed against its own acceptance criteria, this is a time-limited new capability. |
| 8 | Operate the Realtime Quiz platform after go-live: password resets, restarts, monitoring | No | No | No | Operation | User support and monitoring continue after the project hands over the service. |
| 9 | Write and publish the department's annual IT report for the dean by 31 January | Yes | Yes | No | Project | Each report has a deadline and a distinct year's content, although the work repeats annually. |
| 10 | Replace 40 wireless access points in two buildings during the summer break | Yes | Yes | No | Project | It is a bounded replacement effort with a defined quantity, location, and time window. |

## Grey zones

- **Initiative 7 (multi-node scaling):** It could be a project if the sponsor authorises a separate budget, scope, acceptance criteria, and end date. If it is only routine maintenance inside an existing release, it may be treated as operational work. The sponsor's authorisation and definition of “done” would settle the classification.
- **Initiative 9 (annual IT report):** It has a deadline and a unique report each year, which supports classifying each report as a small project; however, the recurring annual process could be managed as an operation. The department's budgeting, ownership, and whether each year's report has a separately approved scope would settle the classification.

## What our project hands over

At go-live in week 14, the project team hands daily operation of Realtime Quiz to the department's designated IT operations staff. They need a deployment and restart runbook, monitoring instructions, backup and restore procedures, and a contact/escalation path for incidents. The team also hands over administrator guidance, known limitations, configuration instructions, and evidence that the pilot and acceptance checks have passed.
