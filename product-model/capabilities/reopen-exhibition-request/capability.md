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
---

# Reopen a request for review

Organizers put a decided or withdrawn request back to submitted for a fresh decision. No email is sent, and any organization profile of the request becomes inactive until it is approved again.
