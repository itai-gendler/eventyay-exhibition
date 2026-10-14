---
entities:
- entity: queued-email
  shows:
  - Subject
  - Recipient
  - Sent at
references:
- kind: code
  role: implementation
  target: exhibition/views.py#EmailSentListView
---

# Sent emails

The emails already sent.
