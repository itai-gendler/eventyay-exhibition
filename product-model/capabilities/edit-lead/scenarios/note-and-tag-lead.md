---
kind: primary
routes:
  api: API
steps:
- text: The Lead scanning app sends a note and tags for the lead
  kind: actor
  actor: lead-scanning-app
  entities: []
  contexts:
    api:
      place: exhibitor-api
- text: The organization profile may scan leads and the lead is its own
  kind: condition
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Lead scanning
  - entity: lead
    effect: reads
    facts:
    - Attendee
  contexts:
    api:
      place: exhibitor-api
- text: The Product keeps the note and tags on the lead, adds new tags to the organization's tags and counts the use of known ones
  kind: product
  actor: lead-scanning-app
  entities:
  - entity: lead
    effect: changes
    facts:
    - Note
    - Tags
  - entity: lead-tag
    effect: creates
    facts:
    - Name
    - Use count
  contexts:
    api:
      place: exhibitor-api
---

# Note and tag a lead

## Trigger

Booth staff add a note and the tag hot to a lead.

## Outcome

The lead keeps the note and tags; the tag is offered again, most used first.
