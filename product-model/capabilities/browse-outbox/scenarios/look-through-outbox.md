---
kind: primary
routes:
  web: Web
steps:
- text: The Request manager opens the outbox
  kind: actor
  actor: request-manager
  entities: []
  contexts:
    web:
      place: organizer-backend::outbox
- text: The Request manager reads each queued email's subject, recipients and send time
  kind: actor
  actor: request-manager
  entities:
  - entity: queued-email
    effect: reads
    facts:
    - Subject
    - Recipient
    - Send at
    - Batch
  contexts:
    web:
      place: organizer-backend::outbox
---

# Look through the outbox

## Trigger

A request manager opens Message center and Outbox.

## Outcome

The manager sees each waiting message with its recipients, subject, creation time and send time.
