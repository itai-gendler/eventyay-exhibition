---
entities:
- entity: sponsor-group
  shows:
  - Name
  collects:
  - Name
  - Level
  - Show on front page
  - Vouchers per sponsor
references:
- kind: code
  role: implementation
  target: exhibition/views.py#SettingsView
---

# Sponsor settings

Exhibition settings: the sponsor groups.
