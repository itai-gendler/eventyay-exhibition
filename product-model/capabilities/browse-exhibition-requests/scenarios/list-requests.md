---
kind: primary
routes:
  web: Web
steps:
- text: The Request manager opens the requests list
  kind: actor
  actor: request-manager
  entities: []
  contexts:
    web:
      place: organizer-backend::requests
- text: The Product lists the requests with the actions each one's state allows
  kind: product
  actor: request-manager
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
    - Exhibitor
    - Sponsor
    - Last updated
    - Edited after acceptance
  contexts:
    web:
      place: organizer-backend::requests
- text: The Request manager reads each exhibition request's name, submitter, type, state and last change
  kind: actor
  actor: request-manager
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
    - Exhibitor
    - Sponsor
    - Last updated
    - Edited after acceptance
  - entity: account
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: organizer-backend::requests
---

# Review the list of requests

## Trigger

A request manager opens Exhibition requests.

## Outcome

The manager sees every request with its submitter, type and state, and which ones were edited after acceptance.
