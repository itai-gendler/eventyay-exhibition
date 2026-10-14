---
kind: primary
routes:
  web: Web
steps:
- text: The Request manager chooses Move back to accepted and confirms
  kind: actor
  actor: request-manager
  entities: []
  contexts:
    web:
      place: organizer-backend::request-review
- text: The Product moves the request back to accepted if it is still confirmed
  kind: product
  actor: request-manager
  entities:
  - entity: exhibition-request
    effect: changes
    from: Confirmed
    to: Accepted
    facts:
    - Last updated
  contexts:
    web:
      place: organizer-backend::request-review
---

# Undo a confirmation

## Trigger

A request manager learns a confirmation was a mistake and chooses Move back to accepted.

## Outcome

The request is accepted and can be confirmed again.

## Edge cases

- If the request changed state meanwhile, nothing is changed and the manager is told.
