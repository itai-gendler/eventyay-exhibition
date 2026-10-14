---
entities:
- entity: organization-profile
  shows:
  - Exhibitor
  - Sponsor
- entity: exhibition-request
  shows:
  - Organization name
  - Exhibitor
  - Sponsor
  - Submitted at
- entity: event
  shows:
  - Call enabled
  - Private call
  - Submission deadline
  - Call open
references:
- kind: code
  role: implementation
  target: exhibition/views.py#DashboardView
---

# Exhibition overview

The landing page of the exhibition area.
