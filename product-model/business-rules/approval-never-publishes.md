---
appliesTo:
- type: capability
  id: approve-exhibition-request
- type: capability
  id: publish-organization
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorPublishView
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitionRequest
---

# Approving a request never publishes its profile

A profile created or brought back by approval is unpublished; it reaches the public site only when an organizer publishes it.

## Rationale

Organizers reveal the exhibition when they are ready, often all at once.
