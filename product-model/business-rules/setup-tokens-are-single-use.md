---
appliesTo:
- type: capability
  id: add-lead-scanning-devices
- type: capability
  id: reset-device-setup-tokens
references:
- kind: code
  role: implementation
  target: exhibition/mail.py#render_device_tokens
---

# Each device's setup token is used once

The access email carries a token only for devices awaiting setup; generating new tokens disconnects devices already scanning.
