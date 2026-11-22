---
name: dispatch-day
description: Review unassigned FieldCamp visits and recommend or confirm a technician assignment. Use for dispatch today, who should take these visits, or find and resolve scheduling conflicts.
---

# Dispatch the day

Read [operating rules](../../shared/operating-rules.md). Confirm branch, service day and timezone. Use the [availability handoff](../../shared/handoffs.md).

When this skill is the fallback for a request to optimize routes, begin the final answer with **Route optimization unavailable** if no optimizer tool is connected. Then give the assignment recommendations.

1. Read the scoped schedule and call `get_dispatch_suggestions` for the day or confirmed visit. Group candidates by unassigned, at risk, or already assigned where the data supports it. Preserve fixed windows and technician commitments.
2. For each suggested assignment, explain the best supported reason such as availability, skill or workload. Cross-check the exact window with `check_team_schedule_conflicts`. Recommend assignments only when branch, eligibility and the visit window are known. If proximity is unknown, say so.
3. Show a change table with visit, current assignment, proposed technician, local time and reason. Ask for approval of exact rows. Re-read each approved visit and recheck conflicts, then call `update_visit` only for the approved fields. Keep unchanged rows and mismatched state out of the write.
4. Verify updated visits and report any that stayed unassigned or need re-review. Use [plan routes](../plan-routes/SKILL.md) for route changes and [urgent slot](../emergency-slot/SKILL.md) when a caller needs service quickly.
