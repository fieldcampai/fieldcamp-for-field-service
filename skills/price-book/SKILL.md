---
name: price-book
description: Find or maintain FieldCamp services, parts, products, categories, units, tax mappings and approved price-book rates. Use to check pricing or prepare a catalog update.
---

# Price book

Read [operating rules](../../shared/operating-rules.md).

1. Resolve branch, currency, SKU or service and unit. Use `get_products_services`, `get_product_service_by_id`, `get_product_categories`, `get_units_of_measurement` and `get_taxes`. Distinguish sale price, internal cost, labor rate and estimate line override.
2. Check duplicates and downstream impact before suggesting changes. Preview SKU, type, old/new price and currency, tax mapping, category, stock setting and effective date where relevant. Ask for the approved value if tax treatment or margins are unclear.
3. After approval, use `create_product_service` or `update_product_service` only with supported fields. If changing the tax catalog itself, use the dedicated admin flow and clarify which existing documents are affected. Verify the catalog entry after the write.
4. For imports or bulk repricing, prepare an itemized review and reconcile duplicate keys before writing. If the tool cannot express the change safely, provide a FieldCamp import or price-book handoff.
