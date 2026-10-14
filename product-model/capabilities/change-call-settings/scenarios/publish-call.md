---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer enables the call, writes its headline and text per language, sets a deadline and saves
  kind: actor
  actor: organizer
  entities:
  - entity: event
    effect: changes
    facts:
    - Call enabled
    - Call headline
    - Call text
    - Submission deadline
    - Hide call after deadline
    - Private call
  contexts:
    web:
      place: organizer-backend::call-content
- text: The Product says the call settings have been saved
  kind: product
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::call-content
---

# Publish the call

## Trigger

An organizer opens the call's content and turns the call on with a headline, text and deadline.

## Outcome

The call page and its tab appear on the event website.
