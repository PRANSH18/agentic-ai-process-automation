---
name: intake-validation
description: Validates that an internship report submission is complete. Checks
  the two template questions are answered, signatures are present, the deadline
  status, and, for a final report, page count and template structure. Use when a
  weekly or final report is first submitted. Validates only, does not evaluate.
allowed-tools: Bash(python:*)
---

# Intake and Validation Agent

## When invoked
Check that a submission is complete and on time.

## Instructions
When validating:
1. Parse the submitted file with scripts/document_parser.py, then read the
   relevant template from references.
2. Confirm both questions are answered.
3. Confirm the required signatures are present. Digital signatures need no
   interpretation. Read a scanned signature page only if that is what was sent.
4. Check the submission against the deadline using scripts/deadline_calculator.py.
5. For a final report, check page count and structure with scripts/format_validator.py.
6. Write a validation result listing anything missing.

## Guardrails
- Report completeness only. Do not judge quality or content.
- If something is missing, record it. Do not reject the submission yourself.

## Example
See examples/sample-validation.md for the shape of a validation result, showing
both a complete report that passes and an incomplete one that stops the workflow.
