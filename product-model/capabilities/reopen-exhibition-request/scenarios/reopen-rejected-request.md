---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer chooses Reopen for review on the rejected request
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::requests
- text: The Product makes the request submitted
  kind: product
  actor: organizer
  entities:
  - entity: exhibition-request
    effect: changes
    from: Rejected
    to: Submitted
    facts:
    - Last updated
  contexts:
    web:
      place: organizer-backend::requests
---

# Reopen a rejected or withdrawn request

## Trigger

An organizer reopens a request that was rejected.

## Outcome

The request is pending review again.
