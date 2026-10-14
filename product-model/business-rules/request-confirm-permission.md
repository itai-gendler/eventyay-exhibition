---
appliesTo:
- type: entity
  id: exhibition-request
  effect: changes
  to: Confirmed
permits:
- related:
  - verb: owns
    entity: applicant
- actors:
  - organizer
  - request-manager
references:
- kind: code
  role: implementation
  target: exhibition/views.py#UserRequestConfirmView
---

# The applicant confirms participation, or those deciding requests confirm for them

An accepted request is confirmed by its applicant through the acceptance email's link, or on their behalf.
