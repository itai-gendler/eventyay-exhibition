---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor opens the Call for Exhibitors tab
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: event-website::call-page
- text: The call is enabled, public and open
  kind: condition
  entities:
  - entity: event
    effect: reads
    facts:
    - Call enabled
    - Private call
    - Call open
  contexts:
    web:
      place: event-website::call-page
- text: The Product shows the call with links to log in or register that lead on to the request form
  kind: product
  actor: visitor
  entities: []
  contexts:
    web:
      place: event-website::call-page
- text: The Visitor reads the call's headline, text and deadline
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

# Read an open call

## Trigger

A visitor opens the Call for Exhibitors tab of the event website.

## Outcome

The visitor reads the call and is asked to log in or create an account to submit a request.
