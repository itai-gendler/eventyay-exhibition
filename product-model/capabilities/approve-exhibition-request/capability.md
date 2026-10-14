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
  target: exhibition/utils.py#create_exhibitor_from_request
- kind: code
  role: implementation
  target: exhibition/views.py#RequestDetailView
- kind: code
  role: implementation
  target: exhibition/views.py#RequestActionView
- kind: code
  role: implementation
  target: exhibition/mail.py#queue_request_email
---

# Approve a request

Organizers accept a submitted or rejected request. Approving creates the organization profile from the request, or brings back the one it had, unpublished, and places an acceptance email with the confirmation link in the outbox.
