---
availability:
- place: organizer-backend
domain: exhibitors-and-sponsors
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorDeviceManageView
- kind: code
  role: implementation
  target: exhibition/utils.py#provision_exhibitor_devices
- kind: code
  role: implementation
  target: exhibition/views.py#queue_exhibitor_access_mail
---

# Add lead-scanning devices

Organizers who may also change the organizer account's settings add devices to an exhibitor, each with its own single-use setup token; if the exhibitor scans leads, an access email with the new tokens is placed in the outbox.
