---
appliesTo:
- type: entity
  id: request-history
  effect: reads
permits:
- actors:
  - organizer
  - request-manager
references:
- kind: code
  role: implementation
  target: exhibition/templates/exhibitors/request_detail.html
---

# Only those deciding requests read a request's history

The history panel of the review page is shown to organizers and request managers.
