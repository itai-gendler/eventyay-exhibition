---
kind: primary
routes:
  web: Web
steps:
- text: The Request manager chooses Reject
  kind: actor
  actor: request-manager
  entities: []
  contexts:
    web:
      place: organizer-backend::request-review
- text: The Product rejects the request
  kind: product
  actor: request-manager
  entities:
  - entity: exhibition-request
    effect: changes
    from: Submitted
    to: Rejected
    facts:
    - Last updated
  contexts:
    web:
      place: organizer-backend::request-review
- text: The Product places the rejection email in the outbox
  kind: product
  actor: request-manager
  entities:
  - entity: queued-email
    effect: creates
    to: In outbox
    facts:
    - Kind
    - Recipient
    - Subject
    - Body
    - Language
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
    - Contact email
  contexts:
    web:
      place: organizer-backend::request-review
---

# Reject a submitted request

## Trigger

A request manager declines a request on its review page.

## Outcome

The request is rejected and the rejection email waits in the outbox.
