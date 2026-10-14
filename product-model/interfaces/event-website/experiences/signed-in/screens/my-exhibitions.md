---
entities:
- entity: organization-profile
  shows:
  - Name
- entity: exhibition-request
  shows:
  - Organization name
references:
- kind: code
  role: implementation
  target: exhibition/dashboard.py#MyExhibitionsView
---

# My Exhibitions

Every exhibition a person takes part in, across events, in their personal dashboard.
