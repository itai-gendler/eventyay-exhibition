---
appliesTo:
- type: entity
  id: queued-email
  effect: changes
  facts:
  - Recipient
  - Subject
  - Body
  - Send at
permits:
- actors:
  - organizer
  - request-manager
  - request-reviewer
references:
- kind: code
  role: implementation
  target: exhibition/views.py#EmailEditView
---

# Only the message center's users change queued emails

Organizers, request managers and request reviewers change a waiting email's recipient, subject, body and send time.
