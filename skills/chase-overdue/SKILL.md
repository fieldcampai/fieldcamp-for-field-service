---
name: chase-overdue
description: Review overdue FieldCamp invoices and draft or send approved reminders. Use for who owes us, unpaid invoice follow-up, or chasing late payments.
---

# Follow up on overdue invoices

Read [operating rules](../../shared/operating-rules.md).

1. Confirm the branch, customer scope and as-of date. Query `get_invoices` in invoice mode for overdue items and read each candidate balance and due date. Verify the remaining balance after partial payments, currency and recipient. Flag disputes, recent payments, or contact restrictions when available. If any of those facts are unknown, report the gap before sending.
2. Show a scoped aging table and prepare a message per eligible customer using only the approved intent. Include confirmed invoice numbers and balance. Show the exact email recipient, subject, body, and document before sending. A general request to chase overdue invoices starts with drafts.
3. After approval refresh payment state, balance and contact. Skip newly settled or materially changed items and ask for review of changed drafts. Send approved messages with `send_document_email` only where the live schema supports the document association and recipient. Report per message as draft, sent/request accepted, failed or needs verification.
