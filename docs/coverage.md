# Field Service coverage

This map covers the service lifecycle and adjacent FieldCamp operations. It distinguishes connector work from steps performed in FieldCamp. A tool identified in source remains a candidate until the installed Claude session exposes it with the required role, scope and compatible schema.

## End-to-end workflows

| Workflow | Entry point | Completion evidence |
|---|---|---|
| [Service request to payment](../skills/service-request-to-payment/SKILL.md) | New intake or existing request, quote, job or invoice | Verified request, offer and acceptance where required, booked and completed visit, invoice, and payment/balance status |
| [Dispatch to closeout](../skills/dispatch-to-closeout/SKILL.md) | Branch’s service day, urgent work, or named visit | Confirmed assignments, verified route state where available, actual visit completion and exceptions |
| [Maintenance renewal](../skills/maintenance-renewal/SKILL.md) | Expiring service agreement or recurring work | Coverage and acceptance evidence, verified recurring schedule and next due date |
| [Customer issue resolution](../skills/customer-issue-resolution/SKILL.md) | Complaint, warranty callback, failed visit or billing question | Documented issue, verified service or finance action, and a named owner for open commitments |
| [Office close](../skills/office-close/SKILL.md) | Day or week close | Job, billing, labor, inventory and sync reconciliation with owner and status for each exception |
| [Connected intake to dispatch](../skills/connected-intake-to-dispatch/SKILL.md) | Smart Booking or Inbox reference | Known owner, deduplicated source/work records, verified appointment or pending callback |

## Operator skills

| Area and skill | Connector path where available | Handoff or dependency |
|---|---|---|
| [Setup](../skills/setup/SKILL.md) | Workspace identity, business hours, teams, job types, model and role visibility | Explicit branch confirmation when the connector cannot identify it |
| [Intake and pipeline](../skills/intake-and-pipeline/SKILL.md) | Search, create or update service request and review configured stages | Unsupported source attribution, linkage or stage transitions |
| [Customers, sites and assets](../skills/customer-sites-and-assets/SKILL.md) | Customer reads and writes, existing custom asset records, record history | Dedicated site creation, merges or advanced linkage if absent |
| [Client brief](../skills/client-brief/SKILL.md) | Customer, upcoming visits, document status, history and open tasks | Inaccessible sources shown as missing |
| [Book a job](../skills/book-a-job/SKILL.md) | Candidate availability, job and visit tools with an explicit booking preview | Service-area or branch eligibility, unavailable writes, and first-visit behavior needing verification |
| [Smart Booking](../skills/smart-booking/SKILL.md) | Verify customer/site/office intake where visible | Booking page, publishing, capacity, territories, and public booking QA |
| [Urgent slot](../skills/emergency-slot/SKILL.md) | Eligibility and availability with approved visit creation | Verified real-time ETA and emergency procedures |
| [Quote a job](../skills/quote-a-job/SKILL.md) | Price book, taxes, request conversion or estimate creation, approved document email | Unsupported draft linkage, signature or document workflow |
| [Schedule approved work](../skills/won-estimate-to-job/SKILL.md) | Verify acceptance and existing jobs; configured conversion and booking | Manual approval/convert path if the workspace rule is unavailable |
| [Manage jobs](../skills/manage-jobs/SKILL.md) | Job and visit updates, valid transitions and rebooking | Unsupported series updates, audit-sensitive cancellation or customer notice |
| [Dispatch the day](../skills/dispatch-day/SKILL.md) | Suggestions, conflict checks, approved assignment and read-back | Unavailable skills/coverage data and external notifications |
| [Route planning](../skills/plan-routes/SKILL.md) | Current dispatch review and conflict checks | Optimizer start/read/apply/discard tools and server-side tenant checks |
| [Field visit](../skills/field-visit/SKILL.md) | Visit status, assignment, documented transitions | GPS/ETA, photos, signatures or other requirements without a tool |
| [Forms and documentation](../skills/field-forms-and-documentation/SKILL.md) | Existing custom inspection/log records, identifiable prerequisites | Native forms, field signatures, attachments and customer document packages |
| [Inspections and field evidence](../skills/inspection-and-compliance/SKILL.md) | Existing trade-specific custom objects and verified linked inspection records | Native evidence forms, required sign-off or formal submission |
| [Change orders and callbacks](../skills/change-orders-and-callbacks/SKILL.md) | Existing scope/document review and supported quote, visit or task changes | Native change-order or warranty records when unsupported |
| [Recurring work](../skills/recurring-work/SKILL.md) | Recurring or multi-day jobs where pattern is supported | Advanced occurrence edits, exceptions and agreement setup |
| [Service agreements](../skills/service-agreements/SKILL.md) | Agreement-equivalent existing records, if configured, and job history | Native agreement, coverage/billing rules and approval controls |
| [Customer Inbox](../skills/customer-inbox/SKILL.md) | Request and customer context, confirmed document email | Scoped Inbox reads and replies where supported |
| [Customer portal](../skills/customer-portal/SKILL.md) | Document/job state and returned approved links | Portal publishing, invitations, permissions and new link generation |
| [Team, calendar and access](../skills/team-calendar-and-access/SKILL.md) | Staff and calendar reads, approved calendar adjustments | Invitations, role changes, branch assignments and staffing configuration |
| [Timesheets and payroll](../skills/timesheets-and-payroll/SKILL.md) | Visit timing for context | Actual punches, time correction, approval, payroll export and earnings |
| [Equipment and fleet](../skills/equipment-and-fleet/SKILL.md) | Existing equipment custom records | Native asset allocations, vehicle location and fleet maintenance data |
| [Stock and purchase orders](../skills/restock/SKILL.md) | Stock, vendors, purchase orders and transfer operations | Unsupported stock movements, receiving or partial fulfillment |
| [Price book](../skills/price-book/SKILL.md) | Product/service lookups and approved catalog changes | Bulk imports, tax administration and specialized pricing |
| [Parts and job costing](../skills/parts-and-job-costing/SKILL.md) | Price book, invoice, inventory and job context | Native job logs, item consumption, actual field labor and costing |
| [Invoice completed work](../skills/invoice-finished-work/SKILL.md) | Completion evidence, eligible invoice creation and separate send | Missing accurate job linkage, eligible draft state or billing evidence |
| [Overdue follow-up](../skills/chase-overdue/SKILL.md) | Balance refresh, approved reminder with supported document email | Unsupported communication channel or unreconciled balance |
| [Manual payment](../skills/record-payment/SKILL.md) | Payment history and receipt recording for funds already received | Actual tender processing and duplicate reconciliation if the state is unknown |
| [Billing adjustments](../skills/billing-adjustments/SKILL.md) | Billing and payment review; eligible draft changes | Credit, refund, write-off, charge or dispute resolution |
| [Accounting and integrations](../skills/accounting-and-integrations/SKILL.md) | FieldCamp-side record and balance checks | OAuth setup, QuickBooks/Xero mapping, sync, exports and external verification |
| [Operations reporting](../skills/ops-report/SKILL.md) | Analytics, visit stats, targeted records | Data coverage, new dashboards, exports or scheduled reporting |
| [Custom records](../skills/custom-records/SKILL.md) | Existing schemas and supported custom record CRUD operations used by the skill | Add or change objects, fields, forms, transitions, or sharing |
| [Automation and data model](../skills/automation-and-data-model/SKILL.md) | Schema inspection and approved existing actions | Workflow authoring, publishing, custom schema updates and live triggers |
| [Workspace administration](../skills/workspace-administration/SKILL.md) | Workspace settings that the connector returns | Departments, franchise, account plan, user access, bulk data and setup |
| [Follow-up tasks](../skills/follow-ups/SKILL.md) | Read, create and update job/client tasks | Unsupported task-field or notification changes |

| [Standalone AI Dispatcher](../skills/dispatcher-operations/SKILL.md) | Independent OAuth connector, job lookup, exact suggestion and outcome | Matching FieldCamp record and deployment-specific tools |
| [Inbox API triage](../skills/inbox-api-triage/SKILL.md) | Narrow Inbox reads, notes, assignments and controlled replies when a scoped Inbox connector is exposed | API-key integration or FieldCamp Inbox handoff when absent from the OAuth bundle |
| [Workspace Workflow Automation](../skills/workspace-workflow-automation/SKILL.md) | Workflow graphs, native trigger/action recipes and approved draft flow if exposed | Native builder or future scoped authoring tool |
| [Franchise HQ](../skills/franchise-operations/SKILL.md) | Branch scoping, standards, intake and network workflow handoffs | Authorized HQ operations, active modules and scoped API adapters |
| [Department rollout](../skills/department-rollout/SKILL.md) | Definition, targeting, branch activation and reporting review | Authorized HQ/branch operation, mappings and department permissions |
| [Analytics API review](../skills/analytics-api-review/SKILL.md) | Existing workspace analytics API/MCP and scoped report readings | Franchise rollup connector or authorized HQ report/export |


[FieldCamp documentation catalog](https://docs.fieldcamp.ai/) · [FieldCamp MCP tools](https://docs.fieldcamp.ai/integrations/mcp-server)
