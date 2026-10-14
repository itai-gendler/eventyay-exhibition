---
appliesTo:
- type: entity
  id: exhibition-request
  effect: changes
  facts:
  - Booth name
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
  target: exhibition/forms.py#ExhibitionRequestReviewForm
---

# The applicant proposes the booth name and those deciding requests may change it

The applicant enters a preferred booth name; organizers and request managers set the booth name while reviewing.
