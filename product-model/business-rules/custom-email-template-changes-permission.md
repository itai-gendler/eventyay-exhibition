---
appliesTo:
- type: entity
  id: custom-email-template
  effect: changes
permits:
- actors:
  - organizer
references:
- kind: code
  role: implementation
  target: exhibition/views.py#EmailTemplatesView
---

# Only organizers change custom email templates

Organizers change the custom email templates.
