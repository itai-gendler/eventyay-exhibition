---
entities:
- entity: queued-email
  shows:
  - Recipient
  - Subject
  - Body
  collects:
  - Body
  - Send at
  - Subject
  - Sent at
references:
- kind: code
  role: implementation
  target: exhibition/views.py#EmailEditView
---

# Email editor

One queued email, to edit before sending or to read once sent.
