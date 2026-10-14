---
appliesTo:
- type: entity
  id: organization-profile
  effect: changes
  facts:
  - Exhibitor
  - Sponsor
  - Sponsor group
  - Booth ID
  - Lead scanning
  - Lead access
  - Voucher access
  - Lead scanning behavior
  - Related sessions
  - Position
permits:
- actors:
  - organizer
- actors:
  - request-manager
  when:
  - state: Inactive
references:
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitorSelfEditForm
- kind: code
  role: implementation
  target: exhibition/utils.py#create_exhibitor_from_request
---

# Only organizers change a profile's type, booth, access and sessions

Whether it exhibits or sponsors, its sponsor group, booth ID, lead scanning, lead and voucher access, lead scanning behavior, related sessions and position are the organizers'. Re-approving a request sets the type, group and booth of its inactive profile.
