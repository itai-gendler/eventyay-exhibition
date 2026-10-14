---
appliesTo:
- type: entity
  id: queued-email
  effect: removes
permits:
- actors:
  - organizer
  - request-manager
  - request-reviewer
references:
- kind: code
  role: implementation
  target: exhibition/views.py#EmailDeleteView
---

# Only the message center's users discard queued emails

Organizers, request managers and request reviewers discard what waits in the outbox.
