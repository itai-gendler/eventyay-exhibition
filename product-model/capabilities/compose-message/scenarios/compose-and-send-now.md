---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer picks organizations, writes the message and chooses Send, or sets Send at
  kind: actor
  actor: organizer
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
    - Email
  contexts:
    web:
      place: organizer-backend::compose
- text: The Product writes the emails and sends them, or schedules them for that time
  kind: product
  actor: organizer
  entities:
  - entity: queued-email
    effect: creates
    to: Scheduled
    facts:
    - Kind
    - Recipient
    - Subject
    - Body
    - Language
    - Batch
    - Send at
  contexts:
    web:
      place: organizer-backend::compose
---

# Send a message at once or later

## Trigger

An organizer writes to chosen organizations and sends it now, or sets a time.

## Outcome

The message is sent now and listed as sent, or waits in the outbox until its time.

## Edge cases

- A time in the past is refused.
- Choosing organizations ignores the state, type and sponsor group filters.
