---
kind: alternative
routes:
  web: Web
steps:
- text: The Order viewer opens Exhibition overview
  kind: actor
  actor: order-viewer
  entities: []
  contexts:
    web:
      place: organizer-backend::overview
- text: The Order viewer reads the number of exhibiting and sponsoring organization profiles
  kind: actor
  actor: order-viewer
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Exhibitor
    - Sponsor
  contexts:
    web:
      place: organizer-backend::overview
---

# An order viewer's overview

## Trigger

An order viewer opens the exhibition.

## Outcome

The order viewer sees how many exhibitors and sponsors there are, without the requests or the call.
