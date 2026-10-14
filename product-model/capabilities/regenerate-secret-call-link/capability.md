---
availability:
- place: organizer-backend
domain: call-content
references:
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitorSettings
- kind: code
  role: implementation
  target: exhibition/views.py#SettingsView
---

# Regenerate the secret call link

Organizers replace a private call's secret link; the old link stops working at once.
