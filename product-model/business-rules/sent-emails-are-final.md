---
appliesTo:
- type: capability
  id: edit-queued-email
- type: capability
  id: discard-queued-email
references:
- kind: code
  role: implementation
  target: exhibition/views.py#EmailEditView
---

# A sent email is never changed or discarded

Only waiting emails can be edited, sent or discarded; sent ones can be read.
