---
name: record-payment
description: Record a cheque, cash payment, or other payment already received on a FieldCamp document. Use for logging a manual payment against a specific invoice or estimate.
---

# Record a manual payment

Read [operating rules](../../shared/operating-rules.md).

1. Find the exact document and read its balance, currency and transaction history with document and payment reads. Confirm the amount, effective date, method and permitted reference. Never request card or bank credentials.
2. Check for a matching transaction. Stop for ambiguity, currency mismatch, unsupported method, amount above the outstanding balance, or uncertain deposit handling. Present invoice, current balance, received amount, date, method and expected balance.
3. After approval and a fresh balance/duplicate check, use `record_payment` once. This logs a payment already received. Verify the new transaction and updated balance, or report an unknown result and reconcile before retrying.
