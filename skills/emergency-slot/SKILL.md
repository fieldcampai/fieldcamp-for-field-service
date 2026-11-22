---
name: emergency-slot
description: Identify qualified FieldCamp technicians and near-term availability for an urgent service call. Use for no heat, outage, emergency repair, or the earliest eligible slot.
---

# Find an urgent slot

Read [operating rules](../../shared/operating-rules.md) and [booking](../book-a-job/SKILL.md).

1. Capture location, service issue, urgency, any site access constraints, and a callback contact. Follow the operator's emergency procedures where applicable. Scheduling establishes a service appointment, so communicate any confirmation separately from immediate safety instructions or emergency response handled by the operator.
2. Confirm branch, timezone, service eligibility and required skills. Query `get_available_team_members_schedule` for the earliest meaningful window and `check_team_schedule_conflicts` for candidates. Use dispatch suggestions for an existing visit when available. Rank by verified capability, readiness and operating constraints. Use distance or ETA only when reliable data gives those values.
3. Present the earliest feasible option and any other reasonable slots. If none exists, offer the next known opening or to prepare an intake handoff for the dispatcher. State if the branch or qualification could not be verified.
4. For an approved booking, follow the booking write and verification steps. Do not displace an existing commitment without an explicit separate change showing who and what would be affected.
