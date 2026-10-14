---
type: web
actors:
- organizer
- request-manager
- request-reviewer
- order-viewer
entryPoints:
- web: /exhibitors/event/{organizer}/{event}
references:
- kind: code
  role: implementation
  target: exhibition/urls.py
- kind: code
  role: implementation
  target: exhibition/templates/exhibitors/base.html
- kind: code
  role: implementation
  target: exhibition/signals.py#exhibition_nav_event_common
---

# Organizer back office

The exhibition area of the event's back office, where the event's team members run the exhibition. Who sees which page follows the permissions of their teams.
