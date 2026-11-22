# Tool map

These names come from the FieldCamp connector source reviewed for this draft. Availability, argument shape, filtering support, scopes, and specific side effects must be checked on the authenticated connector. Claude may namespace tool names. Match to the connected FieldCamp tool by its description as well as its name.

| Area | Candidate tools |
|---|---|
| Workspace and model | `get_company_info`, `get_company_schedule`, `get_teams`, `get_job_types`, `get_data_model` |
| Find records | `search`, `fetch`, `get_filtered_clients`, `get_client_by_id`, `get_client_documents`, `get_client_payment_history`, `get_history` |
| Intake and scheduling | `get_requests`, `get_request_by_id`, `create_client`, `create_request`, `get_next_job_number`, `create_job`, `get_filtered_jobs`, `get_job_by_id`, `get_visits_for_job`, `get_visit_by_id`, `create_visit`, `update_visit` |
| AI dispatch | `get_dispatch_suggestions`, `get_available_team_members_schedule`, `check_team_schedule_conflicts`, `get_calendar_events` |
| Estimates and invoices | `get_products_services`, `get_taxes`, `get_invoices`, `get_invoice_by_id`, `get_document_number`, `convert_request_to_estimate`, `create_document`, `send_document_email` |
| Payments | `get_payment_history`, `record_payment` for manual bookkeeping |
| Custom objects and tasks | `list_object_definitions`, `list_records`, `get_record`, `create_record`, `update_record`, `run_record_action`, `convert_record`, `get_tasks_by_job`, `get_task_by_id`, `create_task`, `update_task` |
| Inventory | `get_inventory`, `get_warehouses`, `get_vendors`, `get_purchase_orders`, `create_purchase_order`, `transfer_inventory` |
| Reporting | `get_analytics`, `get_visit_stats`, `get_filtered_jobs`, `get_invoices` |

## Where the schema matters

- Request-to-estimate conversion copies request lines and marks the request converted in the reviewed source. Confirm both effects. A generic record conversion is valid only for an enabled rule and eligible source stage.
- Visit statuses, transition requirements, job types, and custom object fields come from the workspace. A status accepted by one list filter may have a different representation on a mutation.
- Document listing distinguishes estimates and invoices using the deployed schema. Customer acceptance and document delivery status describe different events. Fetch the record and verify the acceptance field before scheduling.
- Creating a job and creating its first visit may overlap in the product workflow. Read the resulting job and visits before issuing a separate visit create. A job number lookup is not a reservation guarantee.
- Treat send and payment amounts as separate operations. Never provide raw card or bank details to any tool.

## Proposed tools for routes

These four interfaces require implementation and authenticated verification. Use them only if exposed by the connected FieldCamp server and supported by the verified route lifecycle in [plan routes](../skills/plan-routes/SKILL.md).

| Tool | Contract |
|---|---|
| `start_route_plan` | Start a draft for a branch, local service day and optionally selected technicians. Returns plan ID and status. Write. |
| `get_route_plan` | Read status and candidates by plan ID. Returns plan revision, per-tech before and after stops, preserved constraints, excluded work, and available comparison metrics. Read-only. |
| `apply_route_plan` | Apply the reviewed plan ID and revision if current. Returns the applied state and affected visits. Write. |
| `discard_route_plan` | Discard the reviewed draft by ID and revision. Returns the resulting state. Write. |
