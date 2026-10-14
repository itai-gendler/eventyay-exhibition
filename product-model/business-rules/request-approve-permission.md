---
appliesTo:
- type: entity
  id: exhibition-request
  effect: changes
  from: Submitted
  to: Accepted
- type: entity
  id: exhibition-request
  effect: changes
  from: Rejected
  to: Accepted
permits:
- actors:
  - organizer
  - request-manager
references:
- kind: code
  role: implementation
  target: exhibition/views.py#RequestActionView
---

# Only organizers and request managers approve requests

Submitted and rejected requests are approved by those who may change the event's settings or its exhibition requests.
