---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer chooses Reject on the accepted request and confirms
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::requests
- text: The Product rejects the request and makes its organization profile inactive and unpublished
  kind: product
  actor: organizer
  entities:
  - entity: exhibition-request
    effect: changes
    from: Accepted
    to: Rejected
    facts:
    - Last updated
  - entity: organization-profile
    effect: changes
    from: Published
    to: Inactive
    facts: []
  contexts:
    web:
      place: organizer-backend::requests
- text: The Product places the rejection email in the outbox
  kind: product
  actor: organizer
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
  contexts:
    web:
      place: organizer-backend::requests
---

# Reject a request that was accepted

## Trigger

An organizer rejects an accepted request whose profile is already published.

## Outcome

The request is rejected and its organization profile is inactive and off the public site.

## Edge cases

- Rejecting several selected requests at once works the same way and reports the skipped ones.
