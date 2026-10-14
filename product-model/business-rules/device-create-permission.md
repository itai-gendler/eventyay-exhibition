---
appliesTo:
- type: entity
  id: lead-scanning-device
  effect: creates
permits:
- actors:
  - organizer
  when:
  - entity: organizer
    fact: Can change organizer settings
    is: 'Yes'
- actors:
  - organizer
  when:
  - entity: organization-profile
    fact: Lead scanning
    is: 'On'
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorDeviceManageView
- kind: code
  role: implementation
  target: exhibition/views.py#grant_lead_scanning_access
---

# Devices are added by organizers who may change the organizer account's settings, or come with lead scanning

Adding devices by hand needs the organizer account's settings permission as well; a profile that gets lead scanning while it has no device receives the event's default number of devices.
