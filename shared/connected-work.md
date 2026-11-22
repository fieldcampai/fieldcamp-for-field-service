# Connected service operations

## Match the system and workspace first

| Namespace | Owns | What this plugin may do |
|---|---|---|
| FieldCamp | Clients, requests, jobs, visits, documents, stock, and supported reporting in the selected workspace | Read and make specifically approved changes using the connected tool schema |
| FieldCamp AI Dispatcher | Standalone Dispatcher workspace, jobs, suggestions, accepted assignments, schedule and the booking links this workspace exposes | Inspect one authorized job or schedule, propose or confirm an exact approved suggestion, and verify its state |
| FieldCamp Smart Booking | Published web booking settings and resulting FieldCamp intake for the selected branch | Verify returned intake records in FieldCamp. Configure or preview page settings through the supported in-app flow or a dedicated authorized tool |
| Inbox and Franchise HQ | Conversation state, local workflows, HQ controls, department rollouts and network reports | Use a dedicated authorized connection when one exposes the exact scope. Prepare a handoff to the owning screen when needed |

When a tool name exists in multiple servers, use the tool from the intended namespace. Check each workspace or organization independently. An authorized connection does not prove any pairing. If there is no verified mapping between the FieldCamp branch and Dispatcher workspace, keep their records separate and ask the operator to confirm scope. Do not treat a separate Dispatcher job ID as a FieldCamp job ID.

## Correlation and safe takeover

Carry the intake source, event or conversation ID, branch, department, timezone, owning product, source request/job reference, proposed and accepted slot, and the authenticated source of each fact. Carry a confirmation or delivery ID if one exists. Include customer data only when the next operation needs it.

Keep one booking owner. If Smart Booking or a dispatcher already accepted a slot, Claude verifies and reports it. Claude creates another record only when the operator explicitly approves a distinct next action after reconciliation. A callback request, queued dispatch, candidate suggestion, customer agreement, accepted assignment, and verified booking are separate states. On a timeout, reload the source job before any retry. Keep pending and declined suggestions separate.

## When a capability is unavailable

Report **FieldCamp handoff** or **Connector unavailable** and include the exact source record, current state, next authorized action, responsible role and evidence needed to resume. Use an authorized UI or configured integration for product-specific operations whose only route requires app-session authentication. Never request or relay session tokens, paste credentials into chats, or use generic API proxy tools to work around a missing scope.
