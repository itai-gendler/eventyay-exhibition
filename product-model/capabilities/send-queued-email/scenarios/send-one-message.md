---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Send on the message
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::outbox
- text: The Product sends every unsent row of the message and records the sending
  kind: product
  actor: organizer
  entities:
  - entity: queued-email
    effect: changes
    from: In outbox
    to: Sent
    facts:
    - Sent at
  contexts:
    web:
      place: organizer-backend::outbox
---

# Send a message

## Trigger

An organizer chooses Send on an acceptance email in the outbox.

## Outcome

The email is sent and listed under Sent.
