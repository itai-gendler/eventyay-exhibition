---
entities:
- entity: custom-email-template
  collects:
  - Name
  - Subject
  - Body
references:
- kind: code
  role: implementation
  target: exhibition/views.py#CustomEmailTemplateCreateView
---

# Custom template editor

Adding one custom email template.
