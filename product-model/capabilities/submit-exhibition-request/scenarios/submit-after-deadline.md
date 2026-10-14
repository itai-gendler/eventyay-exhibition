---
kind: validation
routes:
  web: Web
steps:
- text: The Applicant opens the request form
  kind: actor
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::signed-in::request-form
- text: The call is not open and they did not come through the current secret link
  kind: condition
  entities:
  - entity: event
    effect: reads
    facts:
    - Call open
    - Private call
  contexts:
    web:
      place: event-website::signed-in::request-form
- text: The Product says the call for exhibitors is closed and returns to the call page
  kind: product
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::signed-in::request-form
---

# The call has closed

## Trigger

An applicant tries to open the request form after the deadline without the secret link.

## Outcome

The applicant is sent back to the call page, told the call is closed; nothing is created.

## Edge cases

- When the call is hidden after its deadline, private without the link, or not enabled, the form answers that it does not exist.
