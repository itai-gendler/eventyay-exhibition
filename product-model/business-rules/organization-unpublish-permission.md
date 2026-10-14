---
appliesTo:
- type: entity
  id: organization-profile
  effect: changes
  from: Published
  to: Unpublished
permits:
- actors:
  - organizer
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorPublishView
---

# Only organizers unpublish organization profiles

Organizers take a published profile off the public event website.
