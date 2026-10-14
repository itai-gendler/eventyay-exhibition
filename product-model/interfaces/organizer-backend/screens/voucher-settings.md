---
entities:
- entity: event
  shows:
  - Exhibitor voucher pool
  - Sponsor voucher pool
  collects:
  - Exhibitor voucher pool
  - Sponsor voucher pool
  - Vouchers per organization
  - Attach voucher list
references:
- kind: code
  role: implementation
  target: exhibition/views.py#SettingsView
---

# Voucher settings

Exhibition settings: the voucher pools and defaults.
