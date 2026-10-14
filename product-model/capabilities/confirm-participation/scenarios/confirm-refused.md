---
kind: validation
routes:
  web: Web
steps:
- text: The Applicant follows the confirmation link
  kind: actor
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::signed-in::participation-confirmation
- text: The exhibition request is not accepted
  kind: condition
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Code
  contexts:
    web:
      place: event-website::signed-in::participation-confirmation
- text: The Product says the request can not be confirmed
  kind: product
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::signed-in::my-requests
---

# Only accepted requests can be confirmed

## Trigger

An applicant follows a confirmation link of a request that is no longer accepted.

## Outcome

Nothing changes; the applicant is told the request can not be confirmed.

## Edge cases

- A request of someone else is not found.
