---
availability:
- place: organizer-backend
domain: outbox
references:
- kind: code
  role: implementation
  target: exhibition/views.py#EmailSendView
- kind: code
  role: implementation
  target: exhibition/views.py#EmailBulkActionView
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitionEmailQueue
- kind: code
  role: implementation
  target: exhibition/tasks.py#send_scheduled_email
---

# Send a queued email

The message center's users send a waiting email, its whole message, the selected ones or all of them; scheduled emails send themselves at their time.
