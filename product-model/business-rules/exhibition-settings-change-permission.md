---
appliesTo:
- type: entity
  id: event
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
  target: exhibition/views.py#EmailTemplatesView
---

# Only organizers change the exhibition settings of an event

The call, the standard fields of the exhibitor form, the shared attendee data, the voucher and lead-scanning defaults and the email templates are changed only by those who may change the event's settings.
