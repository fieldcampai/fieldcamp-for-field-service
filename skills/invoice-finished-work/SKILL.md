---
name: invoice-finished-work
description: Review which completed FieldCamp jobs can be invoiced and prepare approved invoice drafts. Use for invoice finished work, billing review, or jobs finished this week.
---

# Invoice completed work

Read [operating rules](../../shared/operating-rules.md) and [handoff formats](../../shared/handoffs.md).

1. Confirm the billing window, completion event, timezone and branch. Use bounded `get_filtered_jobs` and `get_visits_for_job` reads. Validate an actual completion timestamp or equivalent evidence. A job's scheduled end does not establish completion. Note partial data coverage.
2. Read linked invoices, billing customer, approved prices, taxable items, signatures or other required records, and dispute indicators where available. Hold already billed or unverifiable work. Flag deposits, credits, change orders, and split billing for review when data is incomplete.
3. Show a review table with job, evidence of completion, existing billing, proposed draft amount/currency and hold reason. For approved rows, refresh eligibility, obtain a document number and use `create_document` only if the tool supports the relevant billing linkage, fields and draft state. Where unsupported, provide a handoff for the billing screen.
4. Verify the resulting invoice IDs and totals. After unknown status, reconcile against the job and customer before another write. Send only after a separate preview and approval of each recipient and document as described in [quote a job](../quote-a-job/SKILL.md).
