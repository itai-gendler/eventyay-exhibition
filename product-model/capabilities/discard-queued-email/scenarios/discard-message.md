---
kind: primary
routes:
  web: Web
steps:
- text: The Request manager reads the recipients and confirms discarding the queued email
  kind: actor
  actor: request-manager
  entities:
  - entity: queued-email
    effect: reads
    facts:
    - Recipient
    - Subject
  contexts:
    web:
      place: organizer-backend::outbox
- text: The Product deletes every unsent row of the message
  kind: product
  actor: request-manager
  entities:
  - entity: queued-email
    effect: removes
    from: In outbox
  contexts:
    web:
      place: organizer-backend::outbox
---

# Discard a message

## Trigger

A request manager no longer wants to send a composed message.

## Outcome

The message and all its unsent rows are gone from the outbox.
