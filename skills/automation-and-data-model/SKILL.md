---
name: automation-and-data-model
description: Design or review FieldCamp automations, Smart Kits, pipeline transitions, custom fields, objects, views and record actions. Use to customize a trade workflow or troubleshoot why a stage or automation failed.
---

# Automation and data model

Read [operating rules](../../shared/operating-rules.md).

1. Start with the business event, branch, trigger source, field/object schemas and current stage. Read `get_data_model`, `list_object_definitions` and existing record actions as available. Identify downstream notifications, record creation, callbacks and overlap with existing rules.
2. Draft the trigger, conditions, inputs, transitions, actions, missing-field behavior, actor, and rollback. Include one positive and one negative scenario and how to prevent duplicate writes or loops. Keep custom records distinct from changing their schema.
3. For a known existing rule or action, preview its documented effects and wait for approval. Use `change_stage`, `run_record_action`, or `convert_record` only where configured and permitted. Existing record creation and updates are in [custom records](../custom-records/SKILL.md).
4. Changes to schema, workflow publishing, notification templates, stages or rollout need dedicated connector support or an admin handoff. Hand over the exact configuration and role, with staging verification and rollback steps. Mark as draft until observed on a test record.
