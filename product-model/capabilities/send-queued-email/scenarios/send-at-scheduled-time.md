---
kind: unattended
routes:
  web: Web
steps:
- text: The send time of a scheduled email has come
  kind: condition
  entities:
  - entity: queued-email
    effect: reads
    facts:
    - Send at
  unattended: true
  contexts:
    web:
      place: organizer-backend::outbox
- text: The Product sends the email
  kind: product
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

# Send at the scheduled time

## Trigger

The send time of a scheduled email arrives.

## Outcome

The email is sent without anyone acting; one that was sent, discarded or rescheduled meanwhile is left alone.

## Edge cases

- A failed send is tried again up to five times, a minute apart.
