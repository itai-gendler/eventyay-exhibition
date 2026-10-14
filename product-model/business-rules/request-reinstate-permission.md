---
appliesTo:
- type: entity
  id: exhibition-request
  effect: changes
  from: Withdrawn
  to: Submitted
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
  target: exhibition/views.py#UserRequestReinstateView
---

# The applicant reinstates a withdrawn request, and those deciding requests may reopen it

A withdrawn request goes back to review when its applicant reinstates it or when it is reopened.
