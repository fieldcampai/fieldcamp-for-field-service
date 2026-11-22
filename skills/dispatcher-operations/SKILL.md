---
name: dispatcher-operations
description: Inspect an AI Dispatcher job or suggestion, approve or reject a specific Dispatcher assignment, review available schedules and booking links, and verify the final slot. Use for standalone FieldCamp AI Dispatcher operations.
---

# Standalone AI Dispatcher operations

Read [connected work](../../shared/connected-work.md) and [operating rules](../../shared/operating-rules.md). Use the **FieldCamp Dispatcher** namespace for standalone Dispatcher operations and the **FieldCamp** namespace for main-app dispatch. Verify the intended workspace, source and local timezone.

1. Prefer a direct job lookup by the verified Dispatcher record ID when available. Otherwise use a bounded `list_jobs` query supporting the known job ID, and match the returned record exactly. An initial `create_job` queues or creates work for dispatch. It is a write and needs approval. Check for duplicate intake or an existing job before proposing it.
2. Present candidate suggestion, job reference, technician, date, window, freshness or revision if available, and any provider flags. If queued or no viable candidate, report **Awaiting dispatch** and verify the next owner. If the suggested window differs from the caller's acceptance, get the new window approved.
3. Preview the exact suggestion acceptance or rejection. Use `accept_suggestion` or `reject_suggestion` only when the live schema exposes it and after approval. Re-read the same job and confirm the candidate still matches the offered assignment and window. If stale or a different candidate appears, re-preview. After an unknown result, look up the job before retrying.
4. Read back the assignment or pending state by ID. Report **Booked** only when the tool confirms the accepted assignment and verified slot, otherwise show **Pending** or **Needs verification**. Keep customer notifications separately approved.
5. For schedule review, use scoped read tools with the operator's authorized workspace/period. Whole-workspace re-dispatch, changes to booking links or credit-consuming runs are separate actions. Do not call a general API proxy to upgrade access. Compare standalone booking links with [main-app Smart Booking](../smart-booking/SKILL.md) before configuring anything.

[Dispatcher API access](https://docs.fieldcamp.ai/ai-dispatcher/api-access)
