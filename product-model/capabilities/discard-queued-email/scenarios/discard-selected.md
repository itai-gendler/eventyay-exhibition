---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer selects emails, chooses Discard and confirms
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::outbox
- text: The Product deletes the selected rows and the rest of their messages
  kind: product
  actor: organizer
  entities:
  - entity: queued-email
    effect: removes
    from: Scheduled
  contexts:
    web:
      place: organizer-backend::outbox
---

# Discard the selected emails

## Trigger

An organizer selects several waiting emails and chooses Discard.

## Outcome

After confirming, they are gone; the outbox says how many.
