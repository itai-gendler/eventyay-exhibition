---
kind: alternative
routes:
  web: Web
steps:
- text: The Request reviewer opens Exhibition overview
  kind: actor
  actor: request-reviewer
  entities: []
  contexts:
    web:
      place: organizer-backend::overview
- text: The Request reviewer reads the pending count and the recent exhibition requests
  kind: actor
  actor: request-reviewer
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
    - Submitted at
  contexts:
    web:
      place: organizer-backend::overview
---

# A reviewer's overview

## Trigger

A request reviewer opens the exhibition.

## Outcome

The reviewer sees the requests awaiting review and the recent requests, without the exhibitor and sponsor counts or the call settings.
