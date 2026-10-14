---
kind: validation
routes:
  web: Web
steps:
- text: The Applicant opens Withdraw for a request
  kind: actor
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::signed-in::my-requests
- text: The exhibition request is a draft, rejected or withdrawn
  kind: condition
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Code
  contexts:
    web:
      place: event-website::signed-in::my-requests
- text: The Product says the request can no longer be withdrawn
  kind: product
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::signed-in::my-requests
---

# A rejected request cannot be withdrawn

## Trigger

An applicant opens Withdraw for a request that was rejected or already withdrawn.

## Outcome

Nothing changes; the applicant is told it can no longer be withdrawn.
