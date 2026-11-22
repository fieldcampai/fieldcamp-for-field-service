---
name: custom-records
description: Read or record work against an existing FieldCamp custom object such as a site asset, unit, inspection, or backflow test. Use when a trade workflow relies on workspace-specific custom fields.
---

# Work with custom records

Read [operating rules](../../shared/operating-rules.md).

1. Load the object via `list_object_definitions` and then the actual schema with `get_data_model` where available. Resolve parent/site and asset with `list_records` or `get_record`. Make a clear distinction between the existing schema and a new object the administrator would need to create.
2. Map the operator's inputs to actual field keys, allowed values, units, required fields and relationships. Flag missing readings or supporting evidence. Do not overwrite an earlier inspection simply because it has the same asset. Check date and other record identity.
3. Preview the record fields, object and related records. After approval call `create_record` or `update_record` with the live schema. Verify the stored record and relationships.
4. Use `run_record_action` only on an existing enabled action after showing the action's documented effects and getting separate approval. For unsupported schema changes, provide the field specification for an administrator, keeping the original data unchanged.
