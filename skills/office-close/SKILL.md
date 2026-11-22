---
name: office-close
description: Review end-of-day or weekly FieldCamp office close across incomplete work, unbilled jobs, collections, labor, inventory and accounting exceptions. Use when closing a service day or reconciling the week.
---

# Office close and reconciliation

Read [workflow execution](../../shared/run-a-workflow.md) and [operating rules](../../shared/operating-rules.md). Confirm branch, timezone, reporting period and currency.

1. Start from [operations reporting](../ops-report/SKILL.md). Identify visits awaiting closeout, unbilled work, overdue invoices, unmatched payment activity, timesheet exceptions, stock shortages and integration errors where sources are available.
2. Open the relevant workflow for each exception. Use [invoice completed work](../invoice-finished-work/SKILL.md), [overdue follow-up](../chase-overdue/SKILL.md), [timesheets and payroll](../timesheets-and-payroll/SKILL.md), [restock](../restock/SKILL.md), or [accounting and integrations](../accounting-and-integrations/SKILL.md).
3. Return a reconciliation table with count or amount, coverage, source record, reason and next owner. Mark unavailable sources and avoid extrapolating incomplete records. Do not net amounts across currencies.
4. Gate every action by exact item and owner. Handle authorized actions in the corresponding skill, recheck the output, and flag remaining exceptions. If the user asked only for a close review, stop at the report.

Return the window, coverage, exceptions cleared, unresolved items and the next person responsible for each.
