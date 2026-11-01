---
name: integrity-consistency
description: Checks an internship report for quality against the institute rubric,
  for narrative consistency across the weekly reports, and for alignment between
  the final report and the weekly trail. Produces quality scores and an advisory
  traceability signal for the faculty mentor. Use when a weekly or final report
  needs a consistency, quality, or traceability check. Does not grade, does not
  accuse, and does not take action.
license: MIT
metadata:
  author: Champa University Program Office
  version: "1.0"
allowed-tools: Bash(python:*)
---

# Integrity and Consistency Agent

## When invoked
Assess an internship report for quality and consistency, and produce an
evidence-based traceability signal, all for a human to review.

## Instructions
When checking a report:

1. Read the quality rubric from references/quality-rubric.md and the scoring
   guide from references/rubric-scoring-guide.md.
2. Read the report under review from the data folder.
3. Read the student's prior weekly reports from output/weekly-digests.
4. Score the report against each rubric criterion.
5. Check the weekly reports for a consistent narrative over time.
6. For a final report, compare it against the weekly trail using
   scripts/similarity_checker.py to see how well its content is supported.
7. Produce a traceability signal describing how well the report is evidenced
   by the weekly trail.
8. Write the result to output/integrity-reports as scores and flags only.

## How to read the traceability signal
- Well evidenced: the work appears across the weekly reports in the student's
  own developing account. Treat as credible.
- Thinly evidenced: parts of the final report have little or no trace in any
  weekly report. Flag for the faculty mentor to discuss with the student.
- Do not label any report as AI-written. Detection is unreliable. Report only
  how well the work is evidenced, and leave the judgment to the faculty mentor.

## Guardrails
- Output scores and flags only. Never grade, accept, reject, or sign.
- Never send anything to the student directly.
- If the weekly trail is missing or unreadable, say so and do not infer a
  traceability signal from absence alone.
- Escalate a thinly evidenced report to the faculty mentor. Do not act on it.

## Example
See examples/sample-integrity-report.md for the shape of a completed integrity
report, including rubric scores, a consistency note, and a traceability signal.

## Output
A short integrity report: rubric scores by criterion, a consistency note, and a
traceability signal with the evidence behind it. All for faculty review.
