---
name: smart-booking
description: Review customer self-booking and Smart Booking in FieldCamp, including public booking links, service area, availability, arrival windows, booking form fields and intake verification.
---

# Smart Booking

Read [operating rules](../../shared/operating-rules.md). This skill addresses the customer-facing booking experience. For office booking of a single caller, use [book a job](../book-a-job/SKILL.md).

1. Confirm branch, approved public booking URL if supplied, service types, portal/website entry point, service area, hours, lead time, duration, capacity rules, and confirmation message. Identify whether the page creates a request, a job or a recurring series.
2. Separate office availability read from real customer booking availability. Verify booking configuration and publication only with a dedicated authorized tool or operator-provided FieldCamp settings evidence. Do not infer a branch's public booking URL or test a real customer appointment.
3. Prepare a settings and QA handoff if the live connector lacks authoring tools. Include expected eligible/ineligible addresses, valid/invalid time windows, form and confirmation behavior, and what record the office should see. Use sandbox/test settings and synthetic data for a submission check.
4. Report the verified booking link and test intake ID only when available. Label any change requiring **FieldCamp Settings → Online Booking** and say exactly what to configure and verify. [Online Booking documentation](https://docs.fieldcamp.ai/online-booking)

For a submission that already exists, use [connected intake to dispatch](../connected-intake-to-dispatch/SKILL.md) to establish whether this page created a request, a confirmed visit, or a standalone Dispatcher job. Match actual references before starting work through another channel.
