---
entities:
- entity: organization-profile
  shows:
  - Name
  - Logo
  - Banner
- entity: sponsor-group
  shows:
  - Name
references:
- kind: code
  role: implementation
  target: exhibition/views.py#PublicExhibitorListView
---

# Exhibition

The list of exhibitors on the event website.
