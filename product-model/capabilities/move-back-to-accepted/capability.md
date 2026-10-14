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

# Move a request back to accepted

Organizers undo a confirmation: the request is accepted again and waits for the applicant to confirm.
