---
name: restock
description: Check stock at a FieldCamp warehouse, suggest replenishment, preview a purchase order, or plan an inventory transfer.
---

# Review stock and prepare replenishment

Read [operating rules](../../shared/operating-rules.md).

1. Resolve the warehouse and SKU. Use `get_inventory` and warehouse/vendor reads to check current stock, thresholds, incoming orders, units, and known lead time. State when incoming, reserved, or available quantities are missing.
2. Show low-stock items and suggested actions. For transfers verify source stock, destination and units. For purchase orders confirm approved vendor, quantities and any known cost. Do not promise timing or totals based on incomplete data.
3. Preview the exact transfer or purchase order and whether the operation is a draft, confirmed order or notification based on the live schema. Wait for approval. Recheck the stock and open order state, then use `transfer_inventory` or `create_purchase_order` only for the approved values and supported operation.
4. Verify the returned transfer or purchase order and affected stock where readable. Report status per SKU and hand off any incomplete or uncertain action.
