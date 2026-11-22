# FieldCamp for Field Service

FieldCamp for Field Service helps dispatchers, estimators and office teams turn service requests into scheduled, staffed work. Use the FieldCamp and AI Dispatcher connectors to review customer and job records, prepare estimates, check appointment and technician availability, verify assignments, and prepare billing handoffs. The plugin asks for approval before writes and reads the resulting record to confirm what happened when the connected tools support the operation.

## Get started

1. Add **FieldCamp for Field Service** in Claude. Connect **FieldCamp** and **AI Dispatcher by FieldCamp** as needed using your FieldCamp accounts.
2. Start with “Set us up for FieldCamp. Verify the workspace, branch and timezone and summarize the connector capabilities.”
3. Use the workspace and existing record references confirmed in setup. For features the connector cannot reach, the plugin gives the operator a FieldCamp handoff.

## Optional FieldCamp Voice setup

A FieldCamp Voice account can connect to Claude on its own. This is a separate sign-in administered in Claude’s connector settings.

1. In an individual Claude account, open **Customize → Connectors → Add → Add custom connector**. On Team or Enterprise, an authorized owner or admin adds it in **Organization settings → Connectors → Add → Custom → Web**. Members then connect from **Customize → Connectors**.
2. Name the connector **FieldCamp Voice** and enter `https://voice.fieldcamp.ai/api/v1/mcp/`, including the trailing slash. Use OAuth sign-in. If Claude asks how to register its OAuth client, choose **Register automatically**.
3. Sign in with your FieldCamp Voice account and select the intended Voice organization. Once connected, enable **FieldCamp Voice** in a conversation and try “List my FieldCamp Voice agents.”

[Claude custom connector setup](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp) · [FieldCamp Voice guide](https://docs.fieldcamp.ai/ai-receptionist/voice-app-tour)

## Try these workflows

- “Find the service request I give you, summarize the site and requested work, and give me an estimate draft for review.” Supplies a quote proposal with materials, labor and any missing information. [Quote a job](skills/quote-a-job/SKILL.md)
- “Check tomorrow’s schedule in my confirmed branch. List unassigned visits, identify conflicts and propose assignments for review.” Gives a prioritized dispatch list with known constraints and requests approval before committing an assignment. [Dispatch the day](skills/dispatch-day/SKILL.md)
- “Check the Dispatcher job I give you. Is its appointment confirmed? Show the current state and any accepted assignment.” Uses the job and assignment returned by Dispatcher to distinguish a pending suggestion from a confirmed appointment. [AI Dispatcher operations](skills/dispatcher-operations/SKILL.md)
- “Review this completed FieldCamp job for billing. Check for an existing invoice and show a draft or any evidence still needed.” Checks closeout and reduces duplicate billing work. [Invoice finished work](skills/invoice-finished-work/SKILL.md)

The [workflow map](docs/coverage.md) covers intake, booking, dispatch, field work, closeout, billing, follow-up, Inbox, analytics, operations and franchise management. The [connector guide](docs/connected-apis.md) covers account selection, limitations and troubleshooting.

## Data handling

Task-specific arguments go from Claude to the declared FieldCamp or AI Dispatcher connector. Responses can include customer names and contact details, service locations, technician schedules, jobs, invoices and transaction records. When users approve a supported write, the owning service stores the submitted record. On an approved send, FieldCamp forwards the recipient, message and applicable document to its delivery workflow. Depending on the workspace and channel, that workflow can use Google Gmail, Microsoft Outlook, the workspace’s SMTP provider, Twilio for SMS, or Meta or Twilio for WhatsApp. A notification or synchronization already configured in FieldCamp can also run when a record changes. An accounting reconciliation can read a matching record from a separate connector only when the user requests it and has already authorized that connection. [FieldCamp’s integration and delivery options](https://docs.fieldcamp.ai/integrations/apps-and-integrations-all-fieldcamp-connections) The plugin files have no separate database, telemetry, credential storage or executable hooks. Payment workflows record payments already received, such as cash or cheque, after operator review.

FieldCamp retains data during active use and may archive or anonymize it after an account becomes inactive, subject to legal retention requirements. Claude applies its own privacy and retention terms to conversations. This bundle is intended for field service businesses. For product or security support, contact support@fieldcamp.ai. [FieldCamp privacy policy](https://fieldcamp.ai/privacy-policy/) · [Anthropic privacy policy](https://www.anthropic.com/legal/privacy)
