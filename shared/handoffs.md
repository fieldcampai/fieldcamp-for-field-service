# Workflow handoffs

These are assistant-side formats for previews, receipts, and resumable work. Use the live tool schema for API arguments. Carry trusted FieldCamp IDs and the timestamp of the relevant read or write. A handoff can be displayed in Claude. Persist its relevant fields only in existing FieldCamp records after approval and with a supported schema.

| Field | Meaning |
|---|---|
| Workspace and branch | Confirmed workspace and operational location. Required before a scoped write. |
| Record references | Known request, client, site, job, visit, document, or route plan IDs. Include returned links when available. |
| Status | Draft, awaiting input, awaiting approval, partially applied, applied, or needs verification. |
| Evidence | Tool and source record for material values. Include the branch timezone, date range, and units where relevant. |
| Open items | Missing decisions or fields, the next step, and the role that owns it. |
| Approved scope | Record and material values the user approved in the current conversation. Revalidate before a write. A note or an older handoff is insufficient approval for a changed operation. |
| Receipt | Operation outcome, returned IDs, and verified resulting state. Omit if awaiting a write. |

## Workflow payloads

| Producer → consumer | Carry forward | Pause or degrade |
|---|---|---|
| Intake → booking or quote | Request ID if saved, service address, problem, contact, branch, requested window and unresolved details | Ask for missing required information. Keep the appointment unconfirmed. |
| Availability → booking or dispatch | Job or visit ID, technician or team, skills evidence, window with zone, conflict result and observation time | Recheck immediately before the write. A new conflict voids that proposal. |
| Route preview → route apply | Plan ID, revision or freshness marker, branch, day, per-tech stop order, fixed or excluded stops, unassigned work, travel comparison where available | Stop if revised, stale, or outside the selected branch. Missing travel data can be reported as unavailable. |
| Estimate draft → send or schedule | Document ID or unsaved draft, source request, customer, line items with currency and taxes, recipient for send, customer acceptance evidence for scheduling | Revalidate changed totals and recipient. Acceptance requires verified evidence or an explicit operator attestation with provenance. |
| Completed work → invoice | Job and completed visit evidence, billing customer, approved scope, line items, existing invoices and exception reasons | Hold disputed, already billed, or unverifiable work. |
| Invoice preview → follow-up or payment | Invoice ID, client, current balance and currency, as-of time, due date, recipient or payment reference as applicable | Refresh before the write. An uncertain payment requires transaction reconciliation. |
| Ops summary → follow-up | Branch, window, metric definition, complete or partial coverage, supporting record IDs, suggested owner | Report missing inputs as unavailable. Keep operational recommendations as drafts until separately approved. |

## Example

A caller requests an annual inspection at an existing site on Tuesday. The office team selects the matched service address but the required technician qualification is unknown. After approval, retain the request ID, selected site, preferred Tuesday window in the branch timezone, and the missing qualification. Show **awaiting input**. When the qualification is confirmed, reload that request and check current availability before proposing a visit.
