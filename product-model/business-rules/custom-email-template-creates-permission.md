---
appliesTo:
- type: entity
  id: custom-email-template
  effect: creates
permits:
- actors:
  - organizer
references:
- kind: code
  role: implementation
  target: exhibition/views.py#EmailTemplatesView
---

# Only organizers add custom email templates

Organizers add the custom email templates.
