---
appliesTo:
- type: entity
  id: exhibition-request
  effect: changes
  facts:
  - Answers
permits:
- related:
  - verb: owns
    entity: applicant
- actors:
  - organizer
references:
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitorInfoForm
---

# The applicant and the organizers change a request's answers

The applicant answers the custom fields; organizers correct the answers from the organization profile's editor.
