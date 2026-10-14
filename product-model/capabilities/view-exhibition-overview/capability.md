---
availability:
- place: organizer-backend
references:
- kind: code
  role: implementation
  target: exhibition/views.py#DashboardView
- kind: code
  role: implementation
  target: exhibition/signals.py#exhibition_dashboard_component
---

# View the exhibition overview

The landing page of the organizers' exhibition area: how many exhibitors and sponsors there are, how many requests await review, the most recent requests, the call's status and the outbox.
