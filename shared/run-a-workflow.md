# Run an end-to-end FieldCamp workflow

Use the smallest workflow that satisfies the request. A request that spans quoting, booking, service delivery and billing belongs in a chain. Open each linked member skill as its phase begins. Continue through read-only work until a decision, a missing prerequisite, a write preview, or an unsupported tool requires a pause.

## Establish a single work item

- Identify the correct FieldCamp workspace, branch, timezone, and customer/site before opening or changing records. Use targeted reads. When the user refers to an existing record, retrieve it and check related records before proposing duplicates.
- Record the operator's end state. “Close the job” could mean finish a visit, close the parent job, close a customer conversation, or close billing. Verify the intended event.
- Start with the workflow's current phase, as supported by retrieved records. A quote can be sent but awaiting acceptance. A visit can be marked complete while billing remains open. Show those states separately.

## Move safely between phases

1. **Read.** Reopen the current record and validate branch, user authorization, required fields, and relevant state. Check any pending write from a previous session before proposing another.
2. **Prepare.** Build an explicit preview or handoff with record IDs and confirmed values. If an action requires a FieldCamp screen, say which action and what to enter. Mark the workflow paused at that phase.
3. **Approve.** Request approval for the exact preview. One approval may cover a clearly enumerated batch with unchanged details. Approval to create a quote does not approve sending it, and approval to schedule is unrelated to clocking time, billing, or payments.
4. **Act and verify.** Use the connected FieldCamp tool only when it supports the action. Check the response and read back the record. Tell the operator what is confirmed, what still needs verification, and what comes next. Use the [operating rules](operating-rules.md) for ambiguous responses and retries.
5. **Resume.** Carry forward actual FieldCamp IDs plus the relevant state, timestamp, decision, and unresolved prerequisites using [handoff formats](handoffs.md). In a later conversation, reload the FieldCamp records. Report explicitly when the handoff is only in the conversation.

## Status vocabulary

| State | Use when |
|---|---|
| Ready for review | The proposal has enough verified data for the operator to approve or adjust. |
| Awaiting input | A required fact or decision is missing. |
| Awaiting someone else | A customer, technician, supervisor, or system must act first. |
| FieldCamp handoff | A supported in-app step is needed and Claude prepared the data for it. |
| Partially applied | At least one approved write succeeded and another remains pending. |
| Verified complete | The requested outcome is observable through the tool or a confirmed in-app record. |

A chain can end at any state. Show the current phase, confirmed work, blocker, next owner, and source record. Restart at the last verified phase.
