# Agentic AI Process Automation: Internship Report Verification

**Can a multi-agent system take the manual checking out of internship reporting without taking the judgement away from faculty?**

## The answer

Yes, if the agents verify and the humans decide. The design splits the work across four specialist agents under an orchestrator. A report is only marked "ready for faculty signature" after intake, digest and integrity checks have all completed. No single agent can approve anything on its own, and no agent signs, grades or sends evaluative feedback without a human.

## The process

Students submit a weekly progress report through an 8 to 12 week internship, then a final report signed by their industry and faculty mentors. Today signatures are collected by hand every week, email submission leaves no audit trail, and a faculty mentor cannot realistically read every weekly report for ten to fifteen students. Final report review is slow and inconsistent, and students have no way to test a draft against requirements before submitting. The result is a compliance record rather than real feedback.

## The design

| Agent | Job |
|---|---|
| Orchestrator | Routes each trigger to the right workflow, holds shared state and enforces the sign-off rule |
| Intake and validation | Checks a submission is complete and correctly formatted before anything else runs |
| Weekly digest | Turns each weekly report into a structured summary faculty can scan in seconds |
| Integrity and consistency | Checks the final report against the weekly trail and flags contradictions |
| Feedback nudge | Drafts reminders and feedback for a human to approve |

Workflows run on four triggers: weekly submission, final submission, approaching deadline and a faculty member opening the dashboard.

## What is in this repository

| File | What it is |
|---|---|
| [Design document (PDF)](Internship_Report_Agent_Design.pdf) | Process mapping, problem statement, agent design, decision boundaries, information requirements, workflows and folder design |
| [skills/](skills/) | The SKILL.md specifications for the orchestrator and each specialist agent |

## Why this structure

- **Specialists over one large agent.** Each agent has a narrow job and a clear boundary, which makes failures traceable.
- **Shared material loaded once.** Common rules and templates sit at the top of the folder and are reused, which keeps the system cheap to run.
- **Authenticity handled by evidence, not trust.** The integrity agent compares claims across the whole reporting trail rather than judging a single document in isolation.

---

PGDM coursework (Generative AI for Business), Great Lakes Institute of Management, Chennai. The institution in the design is fictionalised.
