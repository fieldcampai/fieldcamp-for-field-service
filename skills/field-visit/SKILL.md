---
name: field-visit
description: Prepare a technician's FieldCamp visit and manage allowed dispatch, in-transit, arrived, work-in-progress and completion steps. Use for start the job, mark arrived, record visit status, or close out this visit.
---

# Run a field visit

Read [operating rules](../../shared/operating-rules.md), [documentation](../field-forms-and-documentation/SKILL.md), and [time tracking](../timesheets-and-payroll/SKILL.md).

1. Resolve the job and visit by ID. Read the assigned technician or team, local appointment window, site contact/access, job scope, service history, required skills and checklist. Share details appropriate to the caller's role.
2. When asked for ETA or tracking, use observed tracking data only where the authenticated connector exposes it. Otherwise use the booked window as a schedule estimate and direct the operator to FieldCamp's live tracking view. Do not infer location from a status label.
3. For a transition, load `get_data_model` for visits. Verify actual state via `get_visit_by_id`. Locate the requested next edge and its requirements, such as notes, signature, forms or photos. If anything is unknown, identify what needs verifying in FieldCamp. If required evidence is missing, prepare a collection handoff and leave the visit state unchanged.
4. Separate reported work, technician time, parts and the customer acknowledgment. Present the intended state transition, notes, prerequisites and optional follow-up. After approval, call `update_visit` for the actual configured next transition. Do not fabricate attendance, signatures or a chain of intermediate events.
5. Read back the visit. If a sibling visit remains open, leave overall job closeout pending. Hand verified completion and unresolved billing inputs to [invoice completed work](../invoice-finished-work/SKILL.md).
