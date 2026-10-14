---
appliesTo:
- type: entity
  id: sponsor-group
  effect: removes
permits:
- actors:
  - organizer
references:
- kind: code
  role: implementation
  target: exhibition/views.py#SettingsView
- kind: code
  role: implementation
  target: exhibition/api.py#ExhibitorInfoSerializer
---

# Only organizers delete sponsor groups

Organizers delete the event's sponsor groups, in the back office or through the organizer API.
