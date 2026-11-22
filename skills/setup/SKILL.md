---
name: setup
description: Set up FieldCamp in Claude, check which branch and tools are connected, or explain which field-service workflows are ready. Use when a team says set us up, connects or changes a workspace, or asks what Claude can do in FieldCamp.
---

# Set up FieldCamp

Read [operating rules](../../shared/operating-rules.md) and the [tool map](../../shared/tools.md). Setup is a read-only walkthrough.

1. Find the connected FieldCamp server and look for `get_company_info`. If the connector is missing or OAuth is required, give the connection step from the [README](../../README.md) and stop. On denied access, distinguish role or scope problems from a disconnected account when the tool provides enough evidence.
2. Read the workspace identity and base settings with `get_company_info`. Where available, use `get_company_schedule`, `get_teams`, `get_job_types` and targeted `get_data_model` calls to confirm the relevant location, service types, business hours, timezone and pipeline. Ask which branch the operator wants when there is more than one or the connector does not identify it.
3. Check the tools available to this session. Where useful, make bounded read probes. Schema availability indicates the tool exists. It does not establish that an OAuth grant, role, or module permits a write. Classify each workflow with the strongest supported evidence.
4. Ask only for unresolved operating information relevant to the operator's first task. Service-area rules, minimum booking lead time, appointment durations, fixed commitments, price book, invoice approval, and applicable custom objects are useful when the operator needs the corresponding workflow. Carry user-provided rules into the current conversation. Offer a copyable profile for later sessions.
5. Show the readiness table and one next action. Avoid reading bulk customer lists or testing writes during setup. When the operator switches branches or reconnects, verify the new identity before reusing any state.

| Workflow | What to verify | If incomplete |
|---|---|---|
| CRM and client brief | Workspace identity and targeted client read | Ask for a FieldCamp record or reconnect |
| Booking and urgent slot | Branch, job types, timezone, availability and conflict reads | Show a service-request handoff or missing details |
| Dispatch | Visits, suggestions, and conflict check | Show the unassigned queue where available |
| Route optimization | Start, get, apply and discard tools plus branch scope | Offer an availability and dispatch review |
| Estimates and invoices | Request, price book, document reads, draft and send tools | Draft from verified inputs and label any limits |
| Custom records | Module, object schema and read access | Ask for the existing object or link the operator to FieldCamp setup |
| Field visits and evidence | Read actual status and configurable transition gates | Prepare a handoff for missing forms, signatures or tracking |
| Inbox and Smart Booking | First-party tool or verified FieldCamp settings for that capability | Prepare the customer or admin handoff |
| Timesheets, agreements and accounting | Direct source for the relevant records and role scope | Show what can be reviewed and who owns the in-app step |
| Reporting | Metrics, branch filter and date coverage | Report only available metrics and their coverage |

Use **Verified read**, **Tool available, write untested**, **Limited**, or **Unavailable**. End with the workspace, branch, timezone, observed tools or permissions behind each limit, and the first prompt the operator can try.


For connected operations, check the FieldCamp and AI Dispatcher workspaces independently. Use a scoped Dispatcher read to establish the intended workspace before acting. Confirm the pairing between each account and the FieldCamp branch in the authorized UI if the connector does not return it. Report Inbox, Smart Booking authoring and Franchise HQ separately. Read [connected work](../../shared/connected-work.md).
