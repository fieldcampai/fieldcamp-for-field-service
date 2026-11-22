---
name: customer-sites-and-assets
description: Find or update a FieldCamp customer, billing contact, service property, site, or installed asset. Use for multiple locations, duplicate client records, site equipment and customer history.
---

# Customers, sites and assets

Read [operating rules](../../shared/operating-rules.md).

1. Use targeted CRM search and `get_client_by_id` to distinguish the site contact, account owner, property manager, billing contact and service address when several exist. Confirm which access instructions or contact details are needed for the task.
2. Review related jobs, documents or custom asset records with `get_history`, `get_client_documents`, `list_records` and `get_record` as appropriate. Keep serial/model/asset identifiers separate from locations and work-order IDs. Use the actual object relationships.
3. Preview supported create/update operations with `create_client`, `update_client`, or [custom records](../custom-records/SKILL.md). A change to a client address can differ from changing the scheduled job site. Show exactly which record is affected.
4. After approval, write once and verify fields and relationships. For duplicates, prepare a merge review with candidate records and references. Use the authorized FieldCamp merge process if a dedicated connector operation is unavailable. Preserve work history and billing associations.
