---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer reads the queued email
  kind: actor
  actor: organizer
  entities:
  - entity: queued-email
    effect: reads
    facts:
    - Recipient
    - Subject
    - Body
  contexts:
    web:
      place: organizer-backend::email-editor
- text: The Organizer changes the body, sets a send time in the future and saves
  kind: actor
  actor: organizer
  entities:
  - entity: queued-email
    effect: changes
    from: In outbox
    to: Scheduled
    facts:
    - Body
    - Send at
  contexts:
    web:
      place: organizer-backend::email-editor
---

# Edit and schedule an email

## Trigger

An organizer opens the acceptance email waiting in the outbox and adds a personal line.

## Outcome

The email waits with the new text until its send time.
