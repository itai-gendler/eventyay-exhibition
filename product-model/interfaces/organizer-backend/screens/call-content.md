---
entities:
- entity: event
  shows:
  - Secret call link
  collects:
  - Call enabled
  - Call headline
  - Call text
  - Submission deadline
  - Hide call after deadline
  - Private call
references:
- kind: code
  role: implementation
  target: exhibition/views.py#SettingsView
---

# Call content

The call for exhibitors' content and its secret link.
