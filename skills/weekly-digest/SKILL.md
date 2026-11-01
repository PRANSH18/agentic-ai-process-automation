---
name: weekly-digest
description: Summarizes a weekly internship report into a short structured digest
  of work done, learnings, and key themes. Use when a weekly report has passed
  validation. Summarizes only.
allowed-tools: Bash(python:*)
---

# Weekly Digest Agent

## When invoked
Produce a short digest of one weekly report.

## Instructions
When digesting:
1. Read the validated weekly report from the data folder.
2. Read the digest style guide from references/digest-style-guide.md.
3. Summarize the work done and the learnings in a few lines each.
4. Note the main themes of the week.
5. Write the digest to output/weekly-digests using the template in assets.

## Guardrails
- Summarize faithfully. Do not evaluate the quality of the work.
- Keep the digest short. It feeds the dashboard and the integrity trail.

## Example
See examples/sample-digest.md for a worked example showing a weekly report and
the digest produced from it.
