---
name: ops-report
description: Summarize a branch's FieldCamp operations for a day or week with jobs, visits, dispatch exceptions, and invoice status where available.
---

# Summarize operations

Read [operating rules](../../shared/operating-rules.md) and [handoff formats](../../shared/handoffs.md). This workflow is read-only.

1. Confirm branch, timezone, reporting window, and comparison period. Use `get_analytics` and `get_visit_stats` with verified filters. Use bounded record lists for issues that need investigation. Follow pagination for any result used as a total and disclose caps or missing pages.
2. Use consistent definitions. Count jobs and visits separately, include duration or other units, and distinguish invoiced amounts, collected amounts, and outstanding balances. Compare windows only on matching branch, definitions, coverage, and currency. Report missing measurements as unavailable.
3. Return a short scorecard and up to three exceptions requiring a decision. Pair each metric with date coverage, definition, and source tool. Show the underlying record IDs for actionable exceptions. Prepare follow-ups as drafts. If the operator asks to save them, continue in [follow-ups](../follow-ups/SKILL.md).
