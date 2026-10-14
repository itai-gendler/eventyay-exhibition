---
kind: validation
routes:
  web: Web
steps:
- text: The Organizer chooses filters and saves the message
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::compose
- text: No request or chosen organization has an address
  kind: condition
  actor: organizer
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Contact email
  contexts:
    web:
      place: organizer-backend::compose
- text: The Product keeps the form open and says nobody matched
  kind: product
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::compose
---

# Nobody matches

## Trigger

An organizer writes to a state no request is in.

## Outcome

Nothing is written; the organizer is told no applicants matched.
