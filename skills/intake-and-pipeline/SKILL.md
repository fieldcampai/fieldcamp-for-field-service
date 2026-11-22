---
name: intake-and-pipeline
description: Triage a FieldCamp lead or inbound service request, log a caller or referral, find duplicate requests, update a lead stage, or prepare a request for booking or estimating.
---

# Intake and pipeline

Read [operating rules](../../shared/operating-rules.md) and [handoffs](../../shared/handoffs.md).

1. Capture the caller or originating record, customer and service site, problem in the customer's words, requested window, urgency and follow-up owner. Identify whether this is a new lead, an existing job enquiry, a warranty issue or a duplicate.
2. Resolve customer/site and existing requests using `search`, `get_requests` or `get_request_by_id`. Use [customer sites and assets](../customer-sites-and-assets/SKILL.md) if necessary. Preserve the source when known and label any unverified attribution.
3. Read the request schema and actual stage transitions using `get_data_model`. Preview what the request will contain, which stage it will occupy and who owns the next action. Ask for required information or retain it as a draft when no valid create is possible.
4. After approval, use `create_request` or `update_request` with the supported fields. Re-read the record for the ID, stage, owner and linked client. If a stage change has an unmet requirement, report the requirement and stop the change.
5. Use [quote](../quote-a-job/SKILL.md), [booking](../book-a-job/SKILL.md), or [issue resolution](../customer-issue-resolution/SKILL.md) only for the requested next phase. A saved request is distinct from a booked or quoted job.
