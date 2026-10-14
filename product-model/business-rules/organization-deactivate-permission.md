---
appliesTo:
- type: entity
  id: organization-profile
  effect: changes
  to: Inactive
permits:
- actors:
  - organizer
  - request-manager
- related:
  - verb: is approved through
    entity: exhibition-request
  - verb: owns
    entity: applicant
references:
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitionRequest
---

# A profile becomes inactive through its request's withdrawal, rejection or reopening

Those who decide requests make a profile inactive by rejecting, withdrawing or reopening its request; the applicant does by withdrawing it.
