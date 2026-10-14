---
appliesTo:
- type: capability
  id: delete-sponsor-group
- type: entity
  id: sponsor-group
  effect: removes
references:
- kind: code
  role: implementation
  target: exhibition/views.py#SponsorGroupDeleteView
---

# A sponsor group cannot be deleted while organizations belong to it

Organizers first move or remove the group's organizations.
