---
kind: validation
routes:
  web: Web
steps:
- text: The Visitor opens the call address
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: event-website::call-page
- text: The call is private and its secret link was not used
  kind: condition
  entities:
  - entity: event
    effect: reads
    facts:
    - Private call
  contexts:
    web:
      place: event-website::call-page
- text: The Product answers that the page does not exist
  kind: product
  actor: visitor
  entities: []
  contexts:
    web:
      place: event-website::call-page
---

# A private call without its link

## Trigger

A visitor opens the call address of a private call directly.

## Outcome

The page is not found, and no tab for the call appears on the event website.
