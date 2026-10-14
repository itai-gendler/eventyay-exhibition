---
availability:
- place: organizer-backend
domain: outbox
references:
- kind: code
  role: implementation
  target: exhibition/views.py#EmailEditView
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitionEmailQueueForm
---

# Edit a queued email

Before sending, the message center's users change a queued email's recipient, subject, body or send time; for a composed message, the change applies to every unsent row of it.
