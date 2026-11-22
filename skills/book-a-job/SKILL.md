---
name: book-a-job
description: Help a dispatcher turn a customer call or service request into a FieldCamp appointment. Use for booking a caller, scheduling an existing job, or offering times for new service work.
---

# Book a job

Read the [operating rules](../../shared/operating-rules.md), [booking handoff formats](../../shared/handoffs.md), and [tool map](../../shared/tools.md). Scope this workflow to one job or service request at a time.

1. Capture customer reference, service address, issue, preferred time or arrival window, urgency, and callback contact as needed. Find the exact client, site, request, and any existing job with `search` or targeted reads. Ask the operator to resolve ambiguous customers or sites. Use a service address for eligibility and travel, and preserve a distinct billing address.
2. Confirm branch, timezone, job type and duration. Use `get_job_types`, `get_company_schedule` and targeted model reads where available. Verify any applicable service-area policy and technician qualification from FieldCamp or the operator. Flag unverified service eligibility or duration and request the missing input before representing a slot as bookable.
3. Read available technicians for the proposed start/end via `get_available_team_members_schedule`. Apply the known qualification and branch constraints and use `check_team_schedule_conflicts` for the proposed assignment. Show up to three viable windows in local time with any constraints they depend on. A free window does not establish travel feasibility or a customer commitment.
4. If the caller cannot commit, approval is missing, or a required input is open, propose saving a request if allowed and useful. Show what it will contain before calling `create_request`. If there is already a request, reference it. Return an **awaiting input** handoff with the actual request ID if saved.
5. Present the booking preview. Include customer/site, job type, requested work, local start/end, crew, known commitments, and exactly what will be created or updated. Mention any notification that the product may trigger if known. Wait for approval of the displayed booking.
6. Recheck the exact slot. Use existing client and job IDs where verified. If necessary and approved, use `create_client` and `create_job` with only the confirmed fields and required live arguments. Query `get_visits_for_job` after job creation. Use `create_visit` only for a genuinely missing visit, and use `update_visit` only for the already-identified visit and approved change. Stop and re-preview if branch, crew, date, duration, or notification materially changes.
7. Verify the booked visit, including assigned crew and timing, by ID. Report the client/job/visit IDs and returned links. If a job exists but the visit failed, show **partially applied** and use that job ID for the next attempt. Reconcile ambiguous results before retrying.

Example preview for an existing job: “J-104 at 42 Elm. Annual maintenance, Tuesday 9:00–10:30 a.m. America/Toronto with Morgan. Checked at 8:42 a.m. No overlap found. Approve creating this visit?”
