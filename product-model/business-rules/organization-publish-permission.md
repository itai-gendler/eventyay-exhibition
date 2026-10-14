---
appliesTo:
- type: entity
  id: organization-profile
  effect: changes
  to: Published
permits:
- actors:
  - organizer
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorPublishView
---

# Only organizers publish organization profiles

Organizers decide when a profile appears on the public event website.
