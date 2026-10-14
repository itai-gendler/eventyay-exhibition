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
- text: The call is not enabled
  kind: condition
  entities:
  - entity: event
    effect: reads
    facts:
    - Call enabled
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

# No call is published

## Trigger

A visitor opens the call address while the call is not enabled.

## Outcome

The page is not found, even for someone who used a secret link before.
