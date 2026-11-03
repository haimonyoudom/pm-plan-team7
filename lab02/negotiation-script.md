# Negotiation · sponsor asks for all Should features by week 10

## Data sheet (week 4)

| Measure | Value |
|---|---|
| Capacity W5-W10 | 6 weeks × 40 h/week = 240 h |
| Must remaining (300 h total, 148 h done in sprints 1-2) | 152 h |
| Should total (Task 2 rating & planned Should) | 110 h (F09 20 h, F10 30 h, F11 24 h, F12 12 h, F13 24 h) |
| Needed by W10 = Must remaining + Should | 152 h + 110 h = 262 h |
| Shortfall by W10 (zero contingency) | 262 h - 240 h = 22 h (0.55 weeks) |
| Shortfall by W10 (contingency intact, 56 h reserve) | 262 h + 56 h - 240 h = 78 h (1.95 weeks ≈ 2 weeks) |
| Velocity, sprints 1-2 (story points completed) | Sprint 1: 18 pts, Sprint 2: 21 pts -> 19.5 pts avg |

### Synthesis

- Total team capacity available from Week 5 to Week 10 is strictly 240 person-hours (6 weeks × 40 h/week under C-02).
- Completing all 152 remaining Must hours plus all 110 Should hours requires 262 person-hours.
- This creates an immediate deficit of 22 hours with zero contingency reserve and zero allocation for Could features.
- When preserving the project's planned 56-hour buffer (10% contingency), the true deficit is 78 hours (approximately 2 full weeks of team capacity).
- Conclusion: Delivering the entire Should scope alongside Must features by Week 10 is mathematically unfundable within fixed constraints C-01, C-02, and C-06.

---

## Script

*Roles: Sponsor = Head of IT; PM = Project Manager.*

**Turn 1 · Sponsor:** I need every Should feature demonstrable at the open day in week 10. Our competitors just launched a sleek platform, and the department needs to show something polished to prospective students. It is mostly small stuff, so it shouldn't be an issue to include it alongside your current plan. *(Tactic 1: "It is a small change")*

**Turn 2 · PM:** I share your goal of showcasing a competitive and impressive platform at the open day. Looking at our verified data sheet, our available capacity between Week 5 and Week 10 is exactly 240 person-hours across our 6 remaining weeks. Completing our remaining 152 hours of core Must features plus all 110 hours of planned Should features requires 262 hours. That produces an immediate deficit of 22 hours with zero contingency buffer remaining, and a 78-hour deficit if we protect our planned 56-hour safety margin. Adding all 110 hours of Should work into that 240-hour window means we would fall short before open day.

**Turn 3 · Sponsor:** The team can surely work a bit harder for a couple of weeks to make this happen. If each student puts in an extra hour or two on weekends or evenings between now and week 10, that easily closes a 22-hour gap. We really need this open day demo to succeed. *(Tactic 2: "Work a bit harder")*

**Turn 4 · PM:** Our team capacity is governed by constraint C-02, which fixes student effort at 4 developers times 10 hours per week, totaling 40 hours weekly. In our first two sprints, the team delivered 18 and 21 points—an average velocity of 19.5 points per sprint—while maintaining our academic commitments. Pushing beyond 40 hours per week introduces fatigue and threatens constraint C-06, which mandates at least 80% test coverage and under 500 ms broadcast latency. When teams push unapproved overtime, defect rates escalate, consuming the very hours we need for stabilizing WebSocket synchronization.

**Turn 5 · Sponsor:** Other development teams across the faculty manage sudden scope increases like this all the time. The LMS team absorbed three new reporting modules right before their mid-term showcase without pushing back the schedule. Why can't your team do the same? *(Tactic 3: "Other teams manage")*

**Turn 6 · PM:** We base our commitments strictly on our empirical delivery metrics rather than assumptions. Over the past 4 weeks, our team completed 148 hours of complex Must foundation work, averaging 74 hours per 2-week sprint. To absorb all 110 Should hours by Week 10, our delivery rate would need to surge to 43.7 hours per week of pure feature output, leaving zero hours for regression testing, CI maintenance, or bug remediation. Maintaining our planned 56-hour contingency reserve is essential so unexpected network latency issues on campus do not jeopardize the platform.

**Turn 7 · Sponsor:** If you are worried about the numbers, let's just decide later. We can tell the developers to start working on both the Must features and the Should features now. When we reach week 9, we will see where we stand and cut whatever isn't ready. *(Tactic 4: "Decide later")*

**Turn 8 · PM:** Deferring the scope decision would divide our developers' attention across 262 hours of parallel tasks over the next 160 hours of sprint execution. By Week 9, we would have seven partially finished modules instead of fully tested, production-grade features. Under C-06, partially built features fail our automated quality gates and cannot run in a live demonstration. Making a deliberate scope selection today ensures that every feature demonstrated on open day is 100% complete, fully responsive, and thoroughly tested.

**Turn 9 · Sponsor:** I see that trying to pack all 110 hours into week 10 will break the schedule. But I cannot show an unstyled, bare-bones prototype to prospective students and faculty visitors. What can we realistically deliver by week 10 that looks sharp and performs reliably without endangering the week-14 pilot?

**Turn 10 · PM:** Here are two ways to give you a strong, reliable open day within our 240-hour capacity:
- **Counter-proposal 1 (Recommended): High-Impact Scope.** We finish all 152 remaining Must hours, plus F09 Responsive Design (20 h) and F10 Analytics and Reporting (30 h) by Week 10. That totals 202 hours, leaving a solid 38-hour contingency buffer (15.8%) to guarantee performance and zero UI glitches. This displaces F11 CSV/PDF Export (24 h), F12 Real-time Notifications (12 h), and F13 Multimedia Questions (24 h) to the Week 14 pilot release, while Could features remain deferred. Visitors experience a responsive quiz on smartphones and live visual analytics on the presenter screen.
- **Counter-proposal 2: Mocked Analytics Demo Build.** We finish all 152 remaining Must hours and build an 8-hour lightweight demo harness with pre-calculated, mocked analytics charts for the presenter screen. That uses 160 hours, leaving an 80-hour buffer (33.3%). This displaces all real production Should features (F09, real F10, F11, F12, F13 totaling 110 h) to Week 14.

**Turn 11 · Sponsor:** Counter-proposal 1 is definitely the winner. Having live responsive design on students' phones with real-time analytics graphs on the main projector screen gives us the visual punch we need for the open day. Visitors won't care about exporting CSVs or file attachments during a 10-minute booth presentation. Let's lock in Option 1: finish the Must scope plus responsive design and analytics by week 10, and deliver the remaining Should features at the week-14 pilot.

**Turn 12 · PM:** Excellent. I will record this as DR-01 today and update the baseline by W5.
