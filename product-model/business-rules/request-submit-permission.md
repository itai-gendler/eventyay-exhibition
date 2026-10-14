---
appliesTo:
- type: entity
  id: exhibition-request
  effect: changes
  from: Draft
  to: Submitted
permits:
- related:
  - verb: owns
    entity: applicant
references:
- kind: code
  role: implementation
  target: exhibition/views.py#UserRequestEditView
---

# Only the applicant submits their draft

A draft becomes submitted when its applicant submits it.
