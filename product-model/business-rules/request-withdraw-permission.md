---
appliesTo:
- type: entity
  id: exhibition-request
  effect: changes
  to: Withdrawn
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
  target: exhibition/views.py#UserRequestWithdrawView
- kind: code
  role: implementation
  target: exhibition/views.py#RequestActionView
---

# The applicant withdraws their request, and those deciding requests may withdraw it

Submitted, accepted and confirmed requests are withdrawn by their applicant or by organizers and request managers.
