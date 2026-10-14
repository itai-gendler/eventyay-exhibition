---
entities:
- entity: lead-scanning-device
  shows:
  - Name
  - Status
  - Setup token
  collects:
  - Name
  - Setup token
  - Status
  - Revoked
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorDeviceManageView
---

# Lead-scanning devices

One exhibitor's lead-scanning devices.
