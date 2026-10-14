---
kind: validation
routes:
  web: Web
steps:
- text: The Request manager saves changes to a sent email
  kind: actor
  actor: request-manager
  entities: []
  contexts:
    web:
      place: organizer-backend::email-editor
- text: The queued email was already sent
  kind: condition
  entities:
  - entity: queued-email
    effect: reads
    facts:
    - Sent at
  contexts:
    web:
      place: organizer-backend::email-editor
- text: The Product refuses and shows the sent emails
  kind: product
  actor: request-manager
  entities: []
  contexts:
    web:
      place: organizer-backend::sent-emails
---

# A sent email cannot be changed

## Trigger

Someone tries to save changes to an email that was already sent.

## Outcome

Nothing changes; they are told a sent email cannot be edited.

## Edge cases

- A send time in the past and an empty body are refused.
