---
availability:
- place: organizer-backend
- place: organizer-api
domain: exhibitors-and-sponsors
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorDeleteView
- kind: code
  role: implementation
  target: exhibition/signals.py#delete_exhibitor_vouchers
- kind: code
  role: implementation
  target: exhibition/signals.py#revoke_exhibitor_devices
---

# Delete an exhibitor or sponsor

Organizers delete an organization profile. Its unredeemed vouchers are deleted and its lead-scanning devices revoked.
