---
type: api
actors:
- organizer
entryPoints:
- api: /api/v1/organizers/{organizer}/events/{event}/exhibitors/
references:
- kind: code
  role: implementation
  target: exhibition/api.py#ExhibitorInfoViewSet
- kind: code
  role: implementation
  target: exhibition/urls.py
---

# Organizer API

The exhibitors endpoint of the event's REST API, through which the organizers' integrations list, add, change and delete organization profiles.
