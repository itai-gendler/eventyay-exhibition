---
appliesTo:
- type: entity
  id: organization-profile
  effect: changes
  facts:
  - Email
permits:
- actors:
  - organizer
- related:
  - verb: is approved through
    entity: exhibition-request
  - verb: owns
    entity: applicant
references:
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitorSelfEditForm
- kind: code
  role: implementation
  target: exhibition/utils.py#sync_exhibitor_from_request
---

# Organizers and the applicant change a profile's email

Organizers change a profile's email; the contact email of an accepted request is carried onto its profile. The contact of an organizer-added profile cannot change it.
