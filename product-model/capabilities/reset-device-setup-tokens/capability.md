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
  target: exhibition/utils.py#reset_exhibitor_device_setup
---

# Generate new setup tokens

Organizers give an exhibitor's devices new setup tokens; devices that were already scanning are disconnected and must be set up again.
