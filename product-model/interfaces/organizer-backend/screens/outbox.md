---
entities:
- entity: queued-email
  shows:
  - Subject
  - Recipient
  - Send at
  - Batch
references:
- kind: code
  role: implementation
  target: exhibition/views.py#EmailOutboxListView
---

# Outbox

The emails waiting to be sent.
