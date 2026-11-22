---
name: connected-intake-to-dispatch
description: Trace a Smart Booking submission or FieldCamp Inbox enquiry through intake, AI Dispatcher suggestion, booking and FieldCamp follow-up. Use for did this request get booked, follow this web booking into dispatch, or reconcile duplicate intake.
---

# Connected intake to dispatch

Read [cross-product rules](../../shared/connected-work.md), [workflow execution](../../shared/run-a-workflow.md), and [operating rules](../../shared/operating-rules.md).

1. **Identify the source.** Establish the Inbox thread or booking reference, branch and service site. Find any existing FieldCamp request or job through [intake and pipeline](../intake-and-pipeline/SKILL.md). Use [Inbox API triage](../inbox-api-triage/SKILL.md) when scoped tools are visible.
2. **Check which system owns the booking.**
   - **AI Dispatcher.** Use [AI Dispatcher operations](../dispatcher-operations/SKILL.md) to check the mapped workspace and exact job. Verify the resulting assignment and window for any accepted offer. Keep a created or queued job pending until an assignment is verified.
   - **Smart Booking.** Check the branch/work type and what the published page is configured to create. Use [Smart Booking](../smart-booking/SKILL.md). A service request still needs booking. An existing confirmed FieldCamp visit should be read back. A standalone Dispatcher booking link follows Dispatcher, not the main app's Smart Booking rules.
   - **Inbox or office.** Determine whether the conversation already links to a request, job, or visit. Use the supported preview in [book a job](../book-a-job/SKILL.md) when FieldCamp owns the booking and no confirmed visit exists.
3. **Reconcile before writing.** If another channel may have created the job, match exact linked IDs or ask the operator to verify a candidate. Treat matching name/address/time as evidence for potential duplication, and retain both references until confirmed. Do not infer shared calendars or automatic cross-product sync from simultaneous sign-ins.
4. **Confirm the result.** Only mark **Booked** after the owning system returns the accepted assignment or a verified visit with the agreed local window. Save or send a follow-up only after a distinct approval. If the actual result is awaiting customer confirmation, follow-up, pending suggestion or unknown, report that state and give an owner and next step.
5. **Continue from the saved record.** Take the verified job and visit through [dispatch to closeout](../dispatch-to-closeout/SKILL.md), then [request to payment](../service-request-to-payment/SKILL.md) when appropriate. If the work exists only in Dispatcher, verify its FieldCamp equivalent before billing or reporting it there.

Return a status table with source event, owning system, identifiers, branch/timezone, verified appointment or pending action, and next owner. Preserve any uncertainty about the field visit, customer notification, or synchronization.
