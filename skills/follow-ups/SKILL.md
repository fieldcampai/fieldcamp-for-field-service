---
name: follow-ups
description: Review, create, or complete FieldCamp follow-up tasks tied to a job or customer. Use for what's still open, remind the office about this job, or mark this follow-up complete.
---

# Track follow-ups

Read [operating rules](../../shared/operating-rules.md).

1. Resolve the job or client. Read linked tasks with `get_tasks_by_job` or the appropriate targeted read. Present task, verified owner, local due date and status. Surface duplicate or ambiguous tasks before creating another.
2. For a change, show the exact linked record, task title, owner, due date and requested state. Use the configured workspace status values. If assigning an owner or deadline is ambiguous, confirm the value.
3. After approval re-read the task or deduplicate a candidate create. Use `create_task` or `update_task` with the live schema. Verify the returned task ID, linkage and state.
