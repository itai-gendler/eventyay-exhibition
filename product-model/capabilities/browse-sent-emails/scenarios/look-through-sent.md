---
kind: primary
routes:
  web: Web
steps:
- text: The Request reviewer opens Sent and searches by recipient
  kind: actor
  actor: request-reviewer
  entities: []
  contexts:
    web:
      place: organizer-backend::sent-emails
- text: The Request reviewer reads each queued email's subject, recipients and sending time
  kind: actor
  actor: request-reviewer
  entities:
  - entity: queued-email
    effect: reads
    facts:
    - Subject
    - Recipient
    - Sent at
  contexts:
    web:
      place: organizer-backend::sent-emails
- text: The Request reviewer opens one and reads its body
  kind: actor
  actor: request-reviewer
  entities:
  - entity: queued-email
    effect: reads
    facts:
    - Body
  contexts:
    web:
      place: organizer-backend::email-editor
---

# Look through the sent emails

## Trigger

A request reviewer checks what was sent to an applicant.

## Outcome

The reviewer sees the sent messages and reads one.
