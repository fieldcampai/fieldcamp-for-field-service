---
name: team-calendar-and-access
description: Review FieldCamp technician availability, calendar events, team membership, branch assignment, skills, time off, or role/access issues. Use for schedule coverage, block time, or prepare a staffing change.
---

# Teams, calendar and access

Read [operating rules](../../shared/operating-rules.md).

1. Verify the branch, team/member, timeframe and timezone. Use `get_teams`, `get_team_member`, `get_company_schedule`, and `get_calendar_events` where authorized. Collect scheduling constraints, time off and required qualifications without exposing personal reasons unnecessarily.
2. Check overlaps and note which coverage would change. For a calendar block, preview exact time, event, visibility, target team and notification effects. Use `create_calendar_event` or `update_calendar_event` only after approval and verify the event.
3. Changes to team members, skills, role permissions, invitations, or branch boundaries require the corresponding authorized connector tool or a FieldCamp admin handoff. Describe least access needed, affected workflows and responsible owner. Keep permission changes distinct from rescheduling visits.
4. Recheck assignment and calendar coverage where possible. Report any outstanding item for an authorized administrator.
