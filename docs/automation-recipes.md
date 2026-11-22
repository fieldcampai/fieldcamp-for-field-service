# FieldCamp automation recipes

These recipes give the exact workflow sequence, scope and acceptance checks for FieldCamp's builders. Configure them as drafts on the intended branch or HQ workspace. Activation and provider connections depend on the deployment and authorized operator. Test Run can send messages or change records.

## 1. Smart Booking → dispatch → confirmed visit

| Step | Configuration |
|---|---|
| Web entry | In FieldCamp Settings → Online Booking, map the service and branch and verify the service-area and capacity rules. Preview the Smart Booking profile, then submit only in an isolated test setup. |
| Reconciliation | Use [connected intake](../skills/connected-intake-to-dispatch/SKILL.md) to locate the owning job/request and accepted assignment. Keep one owner. Retain source reference and branch in subsequent tasks. |
| Pass | One source event has one primary work record and at most one accepted visit. The office sees matching local time and status. A queued job or unanswered request remains pending. |

## 2. Inbox escalation → office follow-up

| Step | Configuration |
|---|---|
| Trigger | In Settings → Automation → Workflow Automation choose the available Inbox trigger for the intended channel. |
| Condition | Continue for the allowed branch/department and open case. Skip a thread that already has an open callback for the same event. |
| Action | Use the available assignment or follow-up action for the selected trigger. If it can't link the thread and deduplicate, use a scoped Inbox API consumer to upsert an internal note or queue the callback. Keep any customer response a separate approved action. |
| Map | Conversation/event ID, branch, department, callback reason, owner and due time. For API consumption retain the webhook event ID, verify signature and scope, and use a stable key per action on replay. |
| Pass | One Inbox escalation leads to one follow-up. Another customer's thread and events on other channels stay outside the workflow. A duplicate event produces no duplicate note or message. |

## 3. Confirmed work → completion check → billing queue

| Step | Configuration |
|---|---|
| Trigger | **Status Changed**, on the configured Visit or Job completion edge, selecting the entity that owns billing readiness. |
| Condition | Verify required evidence, all required visits complete, eligible billing party and scope, no existing linked invoice or open dispute. If the native action set cannot perform a check, queue a human billing review. |
| Action | Use **Create Follow-Up** or the available equivalent task action and assign billing. Include job ID, visits, completion evidence and any hold. A dedicated invoice action is appropriate only for an approved configuration with verified eligibility and duplicate prevention. |
| Pass | One completed job enters the queue once. Incomplete documentation, partially finished work and already billed jobs stay out. |

## 4. Franchise unrouted intake → HQ → branch owner

| Step | Configuration |
|---|---|
| Template | With HQ workflow support enabled, use **Unrouted lead alert** (`unrouted_intake_alert`) for HQ or **Unrouted leads to branch owners** (`unrouted_branch_alert`) for local recipients. Use only operational nodes the owner is authorized to target. |
| Scope and cadence | Select canary branches and verified HQ membership recipients where applicable. Set the schedule and timezone as the current builder requires. Verify the actual territory/department before accepting a lead assignment. |
| Action | Deliver an internal alert with counts, branch and link or lead references for the responsible owner. A routing alert does not itself change the lead's assigned branch. |
| Pass | Unrouted sample requests appear for the right team. Out-of-scope branch data stays out. Verify execution and branch receipts before expanding. |

## 5. Department rollout → first classified job → network report

| Step | Configuration |
|---|---|
| HQ definition | Define a stable network key, reporting code, work class/trade and explicit target nodes. Start with one branch. |
| Branch | Verify the activation, manager, service area, job type/team mapping, and accounting mapping. Move from pending configuration to active through the branch's own authority. |
| Acceptance fixture | Submit one scoped synthetic job through the intended intake channel. Record expected department stamp on job and visit, and invoice where applicable. Confirm a deliberately unmapped case is visible as Unassigned. |
| HQ report | Review **Network performance → By department**. Use the same period and measured grain. If needed, save a board through the authorized HQ action. Verify the branch total against its department rows and Unassigned. |

## 6. Weekly HQ rollup → threshold follow-up

| Step | Configuration |
|---|---|
| Template | **Weekly network rollup** (`weekly_rollup_summary`). For conditional follow-up where available, use **Threshold alert, owner follow-up when flagged** (`threshold_alert_gated`). |
| Scope and cadence | Selected operational branches, schedule + timezone, HQ membership recipients, channels and metric definition. Choose threshold/direction from the operator's agreed policy. |
| Conditions | Separate stale/missing rollups, exclude them from a misleading zero comparison, and report coverage. Alert branch owners only after the supported condition returns flagged branches. |
| Pass | The test run produces one authorized digest for the intended period. Verify recipients and branch receipts, including no action when the threshold isn't crossed. |

[Workspace Workflow Automation](https://docs.fieldcamp.ai/workflow-automation/workflows-overview) · [Franchise departments](https://docs.fieldcamp.ai/franchise/roll-out-departments-across-branches)
