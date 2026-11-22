---
name: plan-routes
description: Prepare and review route optimization for a FieldCamp branch or technician, compare stop order and travel, or apply an approved route plan. Use for optimize tomorrow's routes and route review requests.
---

# Plan routes

Read the [operating rules](../../shared/operating-rules.md), [handoff formats](../../shared/handoffs.md) and [route tool contracts](../../shared/tools.md).

1. Confirm branch, local service day, timezone, and technicians. Retrieve the relevant baseline schedule. Identify fixed appointments and arrival windows, locked routes, unassigned stops, and exclusion reasons where available. If the operator wants a multi-day range, clarify the individual service days when the tool supports one at a time.
2. Check the connected server for all route operations needed for the requested task. If draft start or retrieval is missing, begin the final answer with **Route optimization unavailable** and name the missing capability. Keep this status visible even when the dispatch review succeeds. Offer to summarize the current schedule and flag conflicts using `get_dispatch_suggestions` and conflict reads. A manual sequence can be labeled as a suggestion. Travel savings require measured tool output.
3. Preview starting a draft, with selected day, branch and crew. After approval call `start_route_plan` once. Return the real plan ID. Use `get_route_plan` to refresh status. If pending, give the plan ID for follow-up. Reuse that ID on a later turn and avoid another start.
4. On a ready plan, show baseline and proposed stop order per technician, time windows, any assignment changes, locks, and omitted visits. Show travel duration or distance using consistent units when the tool supplies comparable before and after measurements. Flag time-window breaches and changed commitments as exceptions.
5. For an apply request, show the specific plan ID/revision and affected visits. Wait for explicit approval. Re-read the plan and verify the expected revision and schedule freshness. If stale or changed, present the new plan. Call `apply_route_plan` only with the reviewed version. Verify by reading the applied plan and affected dispatch visits. Distinguish pending, applied, partially applied and needs verification.
6. If the operator wants to discard, show the draft to be discarded and get approval before `discard_route_plan`. A previously applied route requires a supported reversal flow and a new preview. Keep the dispatcher informed if reversal is unavailable.

Output a per-technician change table, a count of unassigned jobs where known, exceptions needing attention, and the truthful plan state.
