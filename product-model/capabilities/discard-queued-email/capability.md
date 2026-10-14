---
availability:
- place: organizer-backend
domain: outbox
references:
- kind: code
  role: implementation
  target: exhibition/views.py#EmailDeleteView
- kind: code
  role: implementation
  target: exhibition/views.py#EmailBulkActionView
---

# Discard a queued email

The message center's users throw away a waiting email or its whole message, or the selected ones after confirming.
