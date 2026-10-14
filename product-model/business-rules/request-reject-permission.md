---
appliesTo:
- type: entity
  id: exhibition-request
  effect: changes
  to: Rejected
permits:
- actors:
  - organizer
  - request-manager
references:
- kind: code
  role: implementation
  target: exhibition/views.py#RequestActionView
---

# Only organizers and request managers reject requests

Requests are rejected by those who may change the event's settings or its exhibition requests.
