---
appliesTo:
- type: entity
  id: exhibition-request
  effect: changes
  from: Accepted
  to: Submitted
- type: entity
  id: exhibition-request
  effect: changes
  from: Confirmed
  to: Submitted
- type: entity
  id: exhibition-request
  effect: changes
  from: Rejected
  to: Submitted
permits:
- actors:
  - organizer
  - request-manager
references:
- kind: code
  role: implementation
  target: exhibition/views.py#RequestActionView
---

# Only organizers and request managers reopen decided requests

Accepted, confirmed and rejected requests go back to review only when those deciding requests reopen them.
