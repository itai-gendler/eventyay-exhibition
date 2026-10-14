---
availability:
- place: organizer-backend
domain: exhibition-requests
references:
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitionRequest
- kind: code
  role: implementation
  target: exhibition/views.py#RequestActionView
- kind: code
  role: implementation
  target: exhibition/views.py#RequestDetailView
---

# Reject a request

Organizers decline a submitted, accepted or confirmed request. A rejection email is placed in the outbox and any organization profile of the request becomes inactive and leaves the public site.
