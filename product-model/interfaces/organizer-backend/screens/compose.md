---
entities:
- entity: custom-email-template
  shows:
  - Name
- entity: organization-profile
  shows:
  - Name
  - Email
- entity: event
  shows:
  - Email templates
references:
- kind: code
  role: implementation
  target: exhibition/views.py#EmailComposeView
---

# Compose

Writing an email to applicants and organizations.
