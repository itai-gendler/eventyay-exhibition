---
kind: primary
routes:
  web: Web
steps:
- text: The Request manager picks state Accepted and Sponsors only, writes the subject and body per language and saves to the outbox
  kind: actor
  actor: request-manager
  entities:
  - entity: custom-email-template
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: organizer-backend::compose
- text: The Product writes one email per distinct address of the matching requests, in each recipient's language, as one message
  kind: product
  actor: request-manager
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
    - Contact email
    - Code
  - entity: account
    effect: reads
    facts:
    - Email
    - Preferred language
  - entity: queued-email
    effect: creates
    to: In outbox
    facts:
    - Kind
    - Recipient
    - Subject
    - Body
    - Language
    - Batch
  contexts:
    web:
      place: organizer-backend::compose
- text: The Product says how many emails were placed in the outbox and shows it
  kind: product
  actor: request-manager
  entities: []
  contexts:
    web:
      place: organizer-backend::outbox
---

# Write to a group of applicants

## Trigger

A request manager writes to every accepted sponsor.

## Outcome

One message with a row per recipient waits in the outbox.

## Edge cases

- Choosing a custom email template fills in its subject and body.
- Drafts are never written to.
