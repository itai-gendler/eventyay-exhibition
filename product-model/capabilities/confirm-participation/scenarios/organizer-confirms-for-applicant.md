---
kind: alternative
routes:
  web: Web
steps:
- text: The Request manager chooses to confirm on the request's behalf on the review page
  kind: actor
  actor: request-manager
  entities: []
  contexts:
    web:
      place: organizer-backend::request-review
- text: The Product confirms the request if it is still accepted
  kind: product
  actor: request-manager
  entities:
  - entity: exhibition-request
    effect: changes
    from: Accepted
    to: Confirmed
    facts:
    - Last updated
  contexts:
    web:
      place: organizer-backend::request-review
---

# Confirm for the applicant

## Trigger

A request manager hears from an accepted applicant and chooses Confirm for applicant.

## Outcome

The request is confirmed on the applicant's behalf.

## Edge cases

- If the request changed state meanwhile, nothing is changed and the manager is told.
