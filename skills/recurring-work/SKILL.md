---
name: recurring-work
description: Set up or review FieldCamp recurring maintenance, regular appointments, multi-day jobs, seasonal work and future-visit exceptions.
---

# Recurring and multi-day work

Read [operating rules](../../shared/operating-rules.md) and [booking](../book-a-job/SKILL.md).

1. Resolve the source agreement or job, site, job type, timezone, window, assigned crew, cadence and end/renewal rule. Show the next occurrences and explain holidays, blackout periods, daylight-saving effects and single-instance exceptions when known.
2. Compare each proposed date against existing linked work and availability. Verify the deployed schema supports this cadence, recurring start, and any skips. If editing a series, distinguish one occurrence, future occurrences and the entire series.
3. Preview the exact series or multi-day scope plus expected write and notification effects. After approval, use `create_job` with supported recurring or multi-day options only when the connector supports the actual pattern. Use a FieldCamp handoff for advanced series edits, agreement setup or unsupported schedules.
4. Verify the parent job and initial/future visit records. Report the schedule actually created and any occurrences that remain pending. Do not assume renewal, deposit or annual entitlement from recurring appointment dates alone.
