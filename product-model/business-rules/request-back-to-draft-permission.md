---
appliesTo:
- type: entity
  id: exhibition-request
  effect: changes
  to: Draft
permits:
- related:
  - verb: owns
    entity: applicant
references:
- kind: code
  role: implementation
  target: exhibition/views.py#UserRequestEditView
---

# Only the applicant takes a submitted request back to a draft

An applicant may save an undecided request as a draft again.
