---
appliesTo:
- type: entity
  id: lead-scanning-device
  effect: changes
  facts:
  - Revoked
permits:
- actors:
  - organizer
references:
- kind: code
  role: implementation
  target: exhibition/signals.py#revoke_exhibitor_devices
---

# Only organizers revoke lead-scanning devices, by deleting their profile

Deleting an organization profile revokes its devices so they can no longer scan.
