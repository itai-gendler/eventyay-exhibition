---
appliesTo:
- type: entity
  id: queued-email
  effect: changes
  to: Sent
permits:
- actors:
  - organizer
  - request-manager
  - request-reviewer
- unattended: true
references:
- kind: code
  role: implementation
  target: exhibition/views.py#EmailSendView
- kind: code
  role: implementation
  target: exhibition/tasks.py#send_scheduled_email
---

# Only the message center's users send queued emails, apart from scheduled ones

Organizers, request managers and request reviewers send what waits in the outbox; scheduled emails send themselves at their time.
