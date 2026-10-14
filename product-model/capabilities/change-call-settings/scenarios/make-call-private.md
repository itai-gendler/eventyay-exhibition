---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer turns on Make this call private and saves
  kind: actor
  actor: organizer
  entities:
  - entity: event
    effect: changes
    facts:
    - Private call
  contexts:
    web:
      place: organizer-backend::call-content
- text: The Organizer copies the secret call link to share it
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

# Make the call private

## Trigger

An organizer wants only invited organizations to apply.

## Outcome

The call has no public tab and opens only through the secret link shown on the page.

## Edge cases

- A private call still needs the call enabled; otherwise its link stops working.
