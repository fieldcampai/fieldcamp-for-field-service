---
name: service-request-to-payment
description: Run a FieldCamp service request through intake, estimate, booking, field delivery, invoice and payment follow-up. Use for lead to cash, handle this service request end to end, or take this job from request through billing.
---

# Service request to payment

Load [workflow execution](../../shared/run-a-workflow.md), [operating rules](../../shared/operating-rules.md), and [handoffs](../../shared/handoffs.md). Use existing FieldCamp records to locate the current phase. Start from the first missing outcome.

| Phase | Open and apply | Exit evidence |
|---|---|---|
| 1. Intake | [Intake and pipeline](../intake-and-pipeline/SKILL.md) and [customer sites](../customer-sites-and-assets/SKILL.md) | Correct customer, site, service request, owner, requested window and outstanding information |
| 2. Establish scope and price | [Quote a job](../quote-a-job/SKILL.md) | Draft saved when approved. Any email sent is recorded separately. If the work follows a confirmed no-estimate policy, record its basis. |
| 3. Accept and book | [Schedule approved work](../won-estimate-to-job/SKILL.md) and [book a job](../book-a-job/SKILL.md) | Acceptance evidence when required, existing or newly created job, and verified visit with local time and crew |
| 4. Dispatch and complete | [Dispatch to closeout](../dispatch-to-closeout/SKILL.md) | Visit completion and prerequisites verified. Exceptions and callbacks classified. |
| 5. Invoice | [Invoice completed work](../invoice-finished-work/SKILL.md) | Correct billing customer, validated scope, verified invoice and separately authorized delivery when requested |
| 6. Collect and follow up | [Overdue follow-up](../chase-overdue/SKILL.md), [manual payment](../record-payment/SKILL.md), or [follow-ups](../follow-ups/SKILL.md) | Balance and transaction evidence or a follow-up with a clear owner |

## Stop or resume

- Missing service address, scope, or paying party pauses the affected phase. If appropriate, offer to preserve the intake in FieldCamp with approval.
- A request to run the chain starts planning. Preview each material write as its inputs become available. Stop at a customer decision, site attendance, or other real event that has yet to occur.
- On resumption, start from the most recent verified record across request, estimate, job, visit and invoice. Check for records created by a coworker or another session before resuming.
- One service job can have multiple visits and bills. Do not advance the whole job from a single visit without workspace evidence. Never assume an approved estimate is paid or a paid deposit settles the final invoice.

Return the work record IDs, completed phases, next decision and owner. For a completed chain, verify any remaining open balance or follow-up rather than declaring it resolved from earlier phases.
