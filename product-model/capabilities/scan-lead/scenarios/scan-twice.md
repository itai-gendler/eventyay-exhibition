---
kind: edge
routes:
  api: API
steps:
- text: The Lead scanning app sends the scanned badge
  kind: actor
  actor: lead-scanning-app
  entities: []
  contexts:
    api:
      place: exhibitor-api
- text: The organization already has a lead for this attendee
  kind: condition
  entities:
  - entity: lead
    effect: reads
    facts:
    - Attendee
  contexts:
    api:
      place: exhibitor-api
- text: The Product answers that the lead was already scanned, with the attendee details the organization may see
  kind: product
  actor: lead-scanning-app
  entities: []
  contexts:
    api:
      place: exhibitor-api
---

# The attendee was scanned before

## Trigger

Staff scan an attendee the organization already has as a lead.

## Outcome

No second lead is made; the app is told the lead was already scanned.
