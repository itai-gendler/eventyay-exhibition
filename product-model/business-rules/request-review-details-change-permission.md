---
appliesTo:
- type: entity
  id: exhibition-request
  effect: changes
  facts:
  - Exhibitor
  - Sponsor
  - Sponsor group
  - Booth ID
permits:
- actors:
  - organizer
  - request-manager
  when:
  - state: Submitted
references:
- kind: code
  role: implementation
  target: exhibition/views.py#RequestDetailView
---

# Only those deciding requests set the type, sponsor group and booth of a submitted request

Organizers and request managers choose what a request is approved as while it waits for a decision.
