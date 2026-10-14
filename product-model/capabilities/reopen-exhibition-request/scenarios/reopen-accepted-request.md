---
kind: primary
routes:
  web: Web
steps:
- text: The Request manager chooses Reopen for review and confirms
  kind: actor
  actor: request-manager
  entities: []
  contexts:
    web:
      place: organizer-backend::requests
- text: The Product makes the request submitted and its organization profile inactive
  kind: product
  actor: request-manager
  entities:
  - entity: exhibition-request
    effect: changes
    from: Accepted
    to: Submitted
    facts:
    - Last updated
  - entity: organization-profile
    effect: changes
    from: Unpublished
    to: Inactive
    facts: []
  contexts:
    web:
      place: organizer-backend::requests
---

# Reopen an accepted request

## Trigger

A request manager wants to decide an accepted request again.

## Outcome

The request is submitted and its profile inactive and unpublished.
