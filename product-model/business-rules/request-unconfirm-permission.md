---
appliesTo:
- type: entity
  id: exhibition-request
  effect: changes
  from: Confirmed
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

# Only organizers and request managers move a confirmed request back to accepted

A confirmation is undone only by those who decide requests.
