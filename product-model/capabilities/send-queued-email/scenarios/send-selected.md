---
kind: alternative
routes:
  web: Web
steps:
- text: The Request manager selects emails and chooses Send
  kind: actor
  actor: request-manager
  entities: []
  contexts:
    web:
      place: organizer-backend::outbox
- text: The Product sends every selected row and the rest of their messages
  kind: product
  actor: request-manager
  entities:
  - entity: queued-email
    effect: changes
    from: Scheduled
    to: Sent
    facts:
    - Sent at
  contexts:
    web:
      place: organizer-backend::outbox
---

# Send the selected emails

## Trigger

A request manager selects several messages, or every one matching the search, and chooses to send them.

## Outcome

All of them are sent; the outbox says how many.
