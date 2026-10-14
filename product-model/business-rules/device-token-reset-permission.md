---
appliesTo:
- type: entity
  id: lead-scanning-device
  effect: changes
  facts:
  - Setup token
  - Status
permits:
- actors:
  - organizer
  when:
  - entity: organizer
    fact: Can change organizer settings
    is: 'Yes'
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorDeviceManageView
---

# Only organizers who may change the organizer account's settings generate new setup tokens

New setup tokens disconnect devices, so they need the organizer account's settings permission as well.
