---
appliesTo:
- type: entity
  id: organization-profile
  effect: removes
permits:
- actors:
  - organizer
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorDeleteView
- kind: code
  role: implementation
  target: exhibition/api.py#ExhibitorInfoViewSet
---

# Only organizers delete organization profiles

Organizers delete profiles in the back office or through the organizer API.
