---
availability:
- place: organizer-backend
domain: outbox
references:
- kind: code
  role: implementation
  target: exhibition/views.py#EmailOutboxListView
- kind: code
  role: implementation
  target: exhibition/views.py#group_email_entries
---

# Browse the outbox

The emails waiting to be sent, one entry per message with all its recipients, with search and sorting.
