---
entities:
- entity: event
  shows:
  - Email templates
  collects:
  - Email templates
- entity: custom-email-template
  shows:
  - Name
  collects:
  - Subject
  - Body
references:
- kind: code
  role: implementation
  target: exhibition/views.py#EmailTemplatesView
---

# Email templates

The wording of every email and the custom templates.
