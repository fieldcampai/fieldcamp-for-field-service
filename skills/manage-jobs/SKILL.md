---
name: manage-jobs
description: Manage a FieldCamp job after intake, including editing scope, rescheduling, putting work on hold, and cancelling future visits without losing job history.
---

# Manage jobs and visits

Read [operating rules](../../shared/operating-rules.md). Read the job and its visits and distinguish parent job state from appointment state.

1. Confirm whether to change one visit, the job, or future occurrences. Gather the current stage, linked estimate or invoice, attendance state, fixed promises and customer notifications.
2. Use `get_data_model` for valid stages and prerequisites. For a reschedule, follow [booking](../book-a-job/SKILL.md) for timezone, crew and conflicts. For a recurring series, follow [recurring work](../recurring-work/SKILL.md). For a price change, follow [change orders](../change-orders-and-callbacks/SKILL.md).
3. Show before/after state, affected crew, time, billing implications and communications if known. Warn about an unsupported cancellation or unintended scope change by naming the required in-app action. Preserve past visits, approved document references and job history.
4. Apply an approved update with `update_job` or `update_visit` when the live schema supports it. Re-read the affected records. If the requested cancellation is a status change, use the configured transition. Handle any customer message through [Customer Inbox](../customer-inbox/SKILL.md).
