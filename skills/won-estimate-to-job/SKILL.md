---
name: won-estimate-to-job
description: Move an approved FieldCamp estimate into scheduled work. Use when a customer accepted a specific estimate and the operator requests job creation or scheduling.
---

# Schedule approved work

Read [operating rules](../../shared/operating-rules.md) and the [estimate handoff](../../shared/handoffs.md).

1. Find the estimate by ID/number and verify its customer, latest version, selected option, acceptance state, site, and scope. If acceptance came outside FieldCamp, request the operator's attestation with channel and time. State that the FieldCamp approval state is unchanged if it still shows pending. Follow product rules when system acceptance is required for conversion.
2. Find linked jobs and visits. Reuse an existing job or visit when it already represents this estimate and selected option. Read the configured conversion rules and source stage through `get_data_model`; use `convert_record` only when a matching, enabled rule is exposed for this source and target. If conversion is unavailable, preview the supported manual path and disclose any linkage it cannot create.
3. Show the estimate, approved work, job and visit changes, and available appointment window. Wait for approval. Carry the job ID forward into [book a job](../book-a-job/SKILL.md). Recheck availability and record freshness before each write.
4. Verify the resulting job and visits. Report when a job exists and scheduling is incomplete. Recover from the saved job before any new conversion.
