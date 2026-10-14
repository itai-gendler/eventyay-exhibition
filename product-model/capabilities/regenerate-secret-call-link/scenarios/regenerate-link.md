---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Regenerate link
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::call-content
- text: The Product makes a new secret link and records who did it
  kind: product
  actor: organizer
  entities:
  - entity: event
    effect: changes
    facts:
    - Secret call link
  contexts:
    web:
      place: organizer-backend::call-content
- text: The Organizer reads the new secret call link
  kind: actor
  actor: organizer
  entities:
  - entity: event
    effect: reads
    facts:
    - Secret call link
  contexts:
    web:
      place: organizer-backend::call-content
---

# Regenerate the link

## Trigger

An organizer suspects the secret link was passed on and chooses Regenerate link.

## Outcome

A new secret link exists; the old one no longer opens the call.
