---
appliesTo:
- type: entity
  id: exhibition-request
  effect: changes
- type: entity
  id: request-history
references:
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitionRequest
- kind: code
  role: implementation
  target: exhibition/signals.py#exhibition_logentry_display
---

# Every change to an exhibition request is recorded in its history

Who moved the request between which states, who changed which fields, and emails sent to the applicant are recorded with the time.
