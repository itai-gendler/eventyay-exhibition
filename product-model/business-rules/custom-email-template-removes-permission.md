---
appliesTo:
- type: entity
  id: custom-email-template
  effect: removes
permits:
- actors:
  - organizer
references:
- kind: code
  role: implementation
  target: exhibition/views.py#EmailTemplatesView
---

# Only organizers delete custom email templates

Organizers delete the custom email templates.
