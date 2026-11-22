# FieldCamp connectors and supported paths

The plugin declares two FieldCamp-operated remote MCP servers. Connect each product separately and confirm the intended organization, FieldCamp branch and Dispatcher workspace.

| Connector | Endpoint | Role in the plugin |
|---|---|---|
| FieldCamp | `https://mcp.fieldcamp.ai/mcp` | Read customer, request, job, schedule, estimate and billing records. Make specifically approved changes when the connected tool and workspace permit them. |
| AI Dispatcher by FieldCamp | `https://dispatcher.fieldcamp.ai/api/mcp` | Read Dispatcher jobs and schedules, review suggestions and confirm an explicitly approved eligible assignment where supported. |

A FieldCamp record and a Dispatcher record can have different identifiers. Verify a shared reference or ask the operator to confirm the mapping before changing either record.

| Workflow | What to verify |
|---|---|
| Smart Booking | Verify the FieldCamp request, job or visit created by the booking page. Use Online Booking in FieldCamp for settings and preview where there is no dedicated connector tool. |
| Inbox | Verify the authenticated connector exposes the intended thread, notes scope and reply channel. Prepare a human handoff if a scoped operation is unavailable. |
| Analytics | Use metrics returned by the authenticated connector. Confirm date range, branch, metric definition and coverage. Use the authorized dashboard for data absent from the tool. |
| Workflow Automation and Franchise HQ | Use the [builder recipes](automation-recipes.md) to prepare a scoped configuration. Apply it from the owning FieldCamp screen when the connector lacks the operation. |

If sign-in fails, reopen the connector, verify the selected account and check with your FieldCamp workspace administrator about permissions. For a failed write with an unknown result, reopen the exact record before retrying. A missing scope or tool is a handoff to an authorized operator.

[FieldCamp MCP docs](https://docs.fieldcamp.ai/integrations/mcp-server) · [AI Dispatcher API access](https://docs.fieldcamp.ai/ai-dispatcher/api-access) · [Franchise network reporting](https://docs.fieldcamp.ai/franchise/network-performance-reporting)
