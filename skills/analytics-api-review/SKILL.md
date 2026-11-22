---
name: analytics-api-review
description: Build or verify FieldCamp analytics using a workspace MCP metric, office report, or Franchise HQ branch or department report. Use for API-based reports, funnel conversion, revenue, collections, utilization and booking attribution.
---

# Analytics API review

Read [operating rules](../../shared/operating-rules.md), [ops report](../ops-report/SKILL.md), and the [API map](../../docs/connected-apis.md). Confirm the question and whether it needs workspace data, Dispatcher data, or HQ rollups.

1. Specify metric, event grain, source, timezone, date range, comparison period, currency, branch/department scope, and freshness. For channel conversion, distinguish submitted intake, eligible intake, confirmed booking and customer attendance. Use a documented joined cohort when linking these events; otherwise report each count with its time basis.
2. Use FieldCamp `get_analytics`, `get_visit_stats` and targeted scoped reads with supported metrics/groupings. Count unique records at the right grain, disclose pagination and row caps, and keep jobs, visits, invoices, and collections distinct. Treat missing scopes, unrecognized metrics and stale sources as unavailable.
3. For a Franchise HQ report, use a dedicated scoped rollup tool only if available. Otherwise use authorized Network performance/By department results or a supplied export. Verify accessible nodes, period start, timezone, computed timestamp, metric grain and department classification (including Unassigned). Do not reconstruct an HQ rollup by searching unrestricted customer records across workspaces.
4. Report totals and known exclusions with record or metric references. For a digest or board, show the definition, data sources and intended recipients. Save/share/schedule only with a separate authorized operation or a [workflow handoff](../workspace-workflow-automation/SKILL.md).

Output one row per metric and scope, with coverage and source, plus the main operational exception the user can act on. Avoid presenting volume or correlations as causal impact. [Network performance reporting](https://docs.fieldcamp.ai/franchise/network-performance-reporting)
