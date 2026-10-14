---
entities:
- entity: organization-profile
  shows:
  - Name
  - Booth ID
  - Booth name
  - Access key
  - Sponsor group
- entity: sponsor-group
  shows:
  - Name
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorListView
---

# Exhibitors and sponsors

The Exhibitors and Sponsors lists of the back office.
