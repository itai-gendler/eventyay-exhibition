---
domain: exhibitors-and-sponsors
references:
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitorDevice
- kind: code
  role: implementation
  target: exhibition/utils.py#provision_exhibitor_devices
---

# Lead-scanning device

A device an organization's staff set up for lead scanning with a single-use setup token.

## Information kept

- **Name** — the organization's name and a number
- **Setup token** — the single-use token, with its setup URL and QR code
- **Status** — Awaiting setup until its token is used, then Connected
- **Revoked** — whether it can no longer scan
