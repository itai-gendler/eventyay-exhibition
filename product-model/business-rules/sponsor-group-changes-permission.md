---
appliesTo:
- type: entity
  id: sponsor-group
  effect: changes
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

# Only organizers change sponsor groups

Organizers change the event's sponsor groups, in the back office or through the organizer API.
