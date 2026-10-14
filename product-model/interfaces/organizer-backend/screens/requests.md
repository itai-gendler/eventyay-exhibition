---
entities:
- entity: exhibition-request
  shows:
  - Organization name
  - Exhibitor
  - Sponsor
  - Last updated
  - Edited after acceptance
- entity: account
  shows:
  - Name
references:
- kind: code
  role: implementation
  target: exhibition/views.py#RequestListView
---

# Exhibition requests

The organizers' list of requests.
