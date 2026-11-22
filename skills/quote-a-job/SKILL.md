---
name: quote-a-job
description: Prepare a FieldCamp estimate for a service request or job. Use when the operator asks to quote a project, price service work, draft an estimate, or send a reviewed estimate.
---

# Quote a job

Read the [operating rules](../../shared/operating-rules.md), [estimate handoff](../../shared/handoffs.md), and [tool map](../../shared/tools.md).

1. Resolve the exact branch, customer, service address, and request or job. Read the relevant request/job, history and existing estimates. Identify accepted, active, superseded, or duplicate estimates with evidence from the workspace.
2. Summarize the scope and unresolved choices. Look up applicable products/services and taxes with `get_products_services` and `get_taxes`. Use actual records for prices, quantities and units, and label any operator-supplied assumptions. Use comparables as context with their dates and differences. Unknown pricing or tax remains an open question. Save a question or status only when an approved, supported record operation exists.
3. Build a line-by-line preview with item, quantity, unit, rate, tax treatment, currency, total, exclusions, and proposed validity terms. Distinguish approved customer-facing wording from internal cost basis. Use the system-calculated total where available. Make incomplete scope or amounts visible and withhold any firm estimate that depends on those missing values.
4. Choose the supported save path with the operator. If the estimate should reproduce the request's existing lines and taxes, preview `convert_request_to_estimate` including the request-stage change. If different lines are approved, use a supported draft creation path via `get_document_number` and `create_document` only when the schema supports the needed linkage and fields. If it cannot link to the source record, show that limitation before saving. Never convert to save a copy while implying the request stays at its current stage.
5. After approval, save once. Read back the estimate with the verified document ID, status, and total. Resolve applications errors or changed totals before sending. Save the handoff using the actual request and estimate IDs. A timeout requires lookup against the request and numbering before another create.
6. For a send request, show the exact recipient, subject, customer-facing body, estimate and attachment/link choice. Refresh the estimate and recipient; wait for separate approval, then call `send_document_email` when available. Report the send result separately from the draft and actual customer acceptance.

Example output: **Draft estimate E-104 — awaiting operator review.** List scope and verified prices, one open scope question, and source request R-512. A draft without a returned ID is marked **unsaved**.
