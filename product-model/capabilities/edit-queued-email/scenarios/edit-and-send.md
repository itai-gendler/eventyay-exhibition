---
kind: alternative
routes:
  web: Web
steps:
- text: The Request reviewer changes the subject and chooses to save and send
  kind: actor
  actor: request-reviewer
  entities:
  - entity: queued-email
    effect: changes
    from: In outbox
    to: Sent
    facts:
    - Subject
    - Sent at
  contexts:
    web:
      place: organizer-backend::email-editor
---

# Save and send

## Trigger

A request reviewer corrects the subject of a queued email and sends it.

## Outcome

The corrected email is sent.
