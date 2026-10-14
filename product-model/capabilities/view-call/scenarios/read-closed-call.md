---
kind: edge
routes:
  web: Web
steps:
- text: The Visitor opens the call
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: event-website::call-page
- text: The submission deadline has passed
  kind: condition
  entities:
  - entity: event
    effect: reads
    facts:
    - Call open
    - Hide call after deadline
  contexts:
    web:
      place: event-website::call-page
- text: The Product shows the call with Requests are closed and no way to submit
  kind: product
  actor: visitor
  entities: []
  contexts:
    web:
      place: event-website::call-page
---

# The deadline has passed

## Trigger

A visitor opens the call after its submission deadline.

## Outcome

The call says requests are closed, or, when the organizers hide it after the deadline, the page and its tab are gone.

## Edge cases

- With Hide call after deadline on, the page answers that it does not exist.
