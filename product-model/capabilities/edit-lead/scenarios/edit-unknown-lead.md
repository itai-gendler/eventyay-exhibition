---
kind: validation
routes:
  api: API
steps:
- text: The Lead scanning app sends a note
  kind: actor
  actor: lead-scanning-app
  entities: []
  contexts:
    api:
      place: exhibitor-api
- text: The organization has no such lead
  kind: condition
  entities:
  - entity: lead
    effect: reads
    facts:
    - Attendee
  contexts:
    api:
      place: exhibitor-api
- text: The Product answers that the lead was not found
  kind: product
  actor: lead-scanning-app
  entities: []
  contexts:
    api:
      place: exhibitor-api
---

# A lead the organization does not have

## Trigger

The app sends a note for a lead of another organization.

## Outcome

Nothing changes; the app is told the lead was not found.

## Edge cases

- With lead scanning off, the app is refused as when scanning.
