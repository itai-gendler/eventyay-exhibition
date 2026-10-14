---
kind: alternative
routes:
  web: Web
steps:
- text: The Visitor follows the secret call link
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: event-website::call-page
- text: The call is enabled and private and the link is the current one
  kind: condition
  entities:
  - entity: event
    effect: reads
    facts:
    - Call enabled
    - Private call
    - Secret call link
  contexts:
    web:
      place: event-website::call-page
- text: The Product remembers the access for the visitor's visit and shows the call as open
  kind: product
  actor: visitor
  entities: []
  contexts:
    web:
      place: event-website::call-page
- text: The Visitor reads the call
  kind: actor
  actor: visitor
  entities:
  - entity: event
    effect: reads
    facts:
    - Call headline
    - Call text
    - Submission deadline
  contexts:
    web:
      place: event-website::call-page
---

# Open a private call through its secret link

## Trigger

An invited organization follows the secret call link the organizers shared.

## Outcome

The visitor sees the call and may submit a request, even after the deadline, for as long as the link stays current.

## Edge cases

- A regenerated link no longer opens the call, and access remembered from it no longer counts.
