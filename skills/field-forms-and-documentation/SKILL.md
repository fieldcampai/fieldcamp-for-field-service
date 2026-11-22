---
name: field-forms-and-documentation
description: Prepare FieldCamp job forms, technician notes, inspection logs, completion evidence, attachments, signatures, or a customer document package. Use when a visit requires a checklist, photo, certificate, or closeout report.
---

# Forms, evidence, and documentation

Read [operating rules](../../shared/operating-rules.md). Confirm visit/job, branch, existing form template and intended distribution.

1. Retrieve available job metadata and transition requirements with `get_data_model`, plus any existing form or inspection custom object with [custom records](../custom-records/SKILL.md). Identify which evidence is required and whether it is available, explicitly absent or unverified.
2. Draft structured readings, units, observation time, technician details, notes and exceptions from verified evidence. A technician or customer supplies the actual inspection evidence and signature. Keep internal notes out of customer-facing packages.
3. Use an existing custom object only when approved for the workflow and when fields, linkage and retention match. For forms, job logs, signatures, attachments or document packages without an exposed, verified tool, create a handoff with job/visit ID, exact form or package, field values, evidence list and responsible person. Have an authorized operator complete the step in FieldCamp.
4. Verify the saved record through a supported read or operator-provided reference. For a document package, list each included item, its version, and readership. Wait for authorized sending through the supported channel.
