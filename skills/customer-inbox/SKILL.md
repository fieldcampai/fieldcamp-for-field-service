---
name: customer-inbox
description: Review a specific FieldCamp customer message, draft a reply, or prepare a follow-up using the conversation and linked records. Use when asked to triage a customer email or text about a request, job, visit or invoice.
---

# Customer Inbox

Read [operating rules](../../shared/operating-rules.md). Verify the customer, branch, thread, channel and permitted recipients.

1. Read the requested thread through a scoped [FieldCamp Inbox tool](../inbox-api-triage/SKILL.md) when it is available. Use linked customer and job records to establish context. When the connector lacks Inbox access, use the details the operator supplied or point them to the specific FieldCamp Inbox record for review.
2. Identify whether the message concerns intake, an existing appointment, billing, a complaint or internal follow-up. Prepare the response with the exact recipient, message, channel, attachments and proposed changes. Preserve the thread and record references.
3. Show the draft and wait for explicit approval before sending. Use a verified connector action for the requested reply channel. `send_document_email` supports estimate and invoice email where exposed. Hand off other sends to an authorized operator if a supported tool is unavailable.
4. Verify the resulting message or action state. Prepare an owner and due time for any open follow-up. Label draft, accepted send and verified delivery separately.
