---
kind: alternative
routes:
  web: Web
steps:
- text: The Request manager chooses Withdraw on a submitted request and confirms
  kind: actor
  actor: request-manager
  entities: []
  contexts:
    web:
      place: organizer-backend::requests
- text: The Product withdraws the request and updates its row
  kind: product
  actor: request-manager
  entities:
  - entity: exhibition-request
    effect: changes
    from: Submitted
    to: Withdrawn
    facts:
    - Last updated
  contexts:
    web:
      place: organizer-backend::requests
---

# Withdraw a request for the applicant

## Trigger

A request manager withdraws a submitted request from the requests list.

## Outcome

The request is withdrawn; no email is sent to the applicant.
