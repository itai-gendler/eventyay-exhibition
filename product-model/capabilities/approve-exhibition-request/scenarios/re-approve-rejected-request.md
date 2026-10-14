---
kind: alternative
routes:
  web: Web
steps:
- text: The Request manager chooses Approve on the rejected request
  kind: actor
  actor: request-manager
  entities: []
  contexts:
    web:
      place: organizer-backend::requests
- text: The Product accepts the request again
  kind: product
  actor: request-manager
  entities:
  - entity: exhibition-request
    effect: changes
    from: Rejected
    to: Accepted
    facts:
    - Profile at acceptance
    - Last updated
  contexts:
    web:
      place: organizer-backend::requests
- text: The Product makes the existing organization profile active again with the request's type, group and booth
  kind: product
  actor: request-manager
  entities:
  - entity: organization-profile
    effect: changes
    from: Inactive
    to: Unpublished
    facts:
    - Exhibitor
    - Sponsor
    - Sponsor group
    - Booth ID
    - Booth name
  contexts:
    web:
      place: organizer-backend::requests
- text: The Product places the acceptance email in the outbox
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
  contexts:
    web:
      place: organizer-backend::requests
---

# Approve a request that was rejected

## Trigger

A request manager changes their mind about a rejected request that had been accepted before.

## Outcome

The request is accepted again and its organization profile is active again, still unpublished until someone publishes it.
