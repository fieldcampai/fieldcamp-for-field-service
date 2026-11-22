---
name: workspace-workflow-automation
description: Build a FieldCamp workflow automation for a workspace using record changes, scheduled work, Inbox activity or missed calls. Use for create a workflow, automate a follow-up, or troubleshoot a workflow run.
---

# Workspace Workflow Automation

Read [operating rules](../../shared/operating-rules.md) and [builder recipes](../../docs/automation-recipes.md). Verify branch, department, operator permission, and whether the target is a local workflow or a Franchise HQ workflow.

1. Find the event and record that truly owns the trigger. For an Inbox trigger bind the intended channel. For a record trigger confirm object, from/to stage or watched field, and avoid an update loop caused by the workflow itself.
2. Draft the actual graph as trigger → conditions → action(s) with inputs and outcomes. Choose only actions shown for that trigger/object. Define correlation key, repeat behavior, owner, credentials/connectivity prerequisites, write scope and manual fallback. Treat any messaging or accounting action as an explicit side effect.
3. Preview definition and affected scope. If a dedicated scoped authoring tool is available, verify the target and save a draft only after approval. Otherwise give the builder recipe with trigger and action labels, field mappings, expected run output and the concrete FieldCamp location. App-session APIs require an authorized first-party integration. Existing custom record actions are distinct from authoring a scheduled or event-triggered workflow.
4. Test with known synthetic records and controlled recipients. Native **Test Run can execute real actions**. Confirm its actual scope before running. Inspect the run and each action receipt, including partial failures and no-op outcomes. Compare with the negative fixture and repeated-event case.
5. Preview activation separately and require explicit approval. Check the saved definition/version, intended branches, schedule and matching rules. Verify active state and first receipt where accessible. For failures, re-read downstream records before replaying.

Return the workflow ID/version if saved, draft/active/test status, trigger to final-result map, and any blocked action. [Workflow builder](https://docs.fieldcamp.ai/workflow-automation/building-workflows)
