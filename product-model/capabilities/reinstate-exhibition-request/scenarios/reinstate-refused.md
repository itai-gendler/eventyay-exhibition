---
kind: validation
routes:
  web: Web
steps:
- text: The Applicant opens Reinstate for a request
  kind: actor
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::signed-in::my-requests
- text: The exhibition request is not withdrawn
  kind: condition
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Code
  contexts:
    web:
      place: event-website::signed-in::my-requests
- text: The Product says the request can no longer be reinstated
  kind: product
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::signed-in::my-requests
---

# Only withdrawn requests can be reinstated

## Trigger

An applicant opens the reinstate page of a request that is not withdrawn.

## Outcome

Nothing changes; the applicant is told the request can no longer be reinstated.
