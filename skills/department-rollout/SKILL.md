---
name: department-rollout
description: Create or roll out a FieldCamp department, prepare branch activation, review coverage, map job types or accounting, and reconcile department reporting. Use for add HVAC or plumbing as an operating department across branches.
---

# Department rollout and reporting

Read [operating rules](../../shared/operating-rules.md), [Franchise HQ](../franchise-operations/SKILL.md) where applicable, and the [API map](../../docs/connected-apis.md).

1. Resolve the **definition** and each **workspace activation** independently. For a local company department, use the workspace's current definitions and permissions. For a network department, find its HQ definition, stable network key, trade/work class, reporting code and ownership.
2. Preview the target branches explicitly. Check operating workspaces, territory/job type/classification overlaps, existing activations, successor/retired definitions and accounting mapping. Recommend one canary branch before a staged roll-out. Do not assume HQ permission grants access to all nodes.
3. Separate HQ definition, target assignments, and branch activation. A targeted department may be **Pending configuration** until a branch with authority assigns its manager, skills/techs, service areas, job types and account mappings. Use the approved HQ or branch tooling when exposed. Otherwise give the exact in-app owner and next step. Re-targeting the same branch should not create a second activation.
4. Validate a synthetic intake from an assigned service channel or job type through a department-stamped job/visit. Confirm unclassified or overlapping work is handled, and keep historical reporting assignments stable unless reclassification is intentionally approved.
5. Use [analytics API review](../analytics-api-review/SKILL.md) to report coverage and performance. Use each metric's actual grain. Reconcile branch totals against department rows and Unassigned where available. A missing or restricted rollup is unknown, not zero.

[Roll out departments across branches](https://docs.fieldcamp.ai/franchise/roll-out-departments-across-branches)
