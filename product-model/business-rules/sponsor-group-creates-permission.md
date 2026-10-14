---
appliesTo:
- type: entity
  id: sponsor-group
  effect: creates
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

# Only organizers add sponsor groups

Organizers add the event's sponsor groups, in the back office or through the organizer API.
