---
kind: primary
routes:
  api: API
steps:
- text: The Lead scanning app sends the scanned badge, scan type and device name with the access key
  kind: actor
  actor: lead-scanning-app
  entities: []
  contexts:
    api:
      place: exhibitor-api
- text: The organization profile may scan leads
  kind: condition
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Lead scanning
  contexts:
    api:
      place: exhibitor-api
- text: The Product records the lead with the attendee details the event shares and the booth at the time
  kind: product
  actor: lead-scanning-app
  entities:
  - entity: lead
    effect: creates
    facts:
    - Attendee
    - Scanned at
    - Scan type
    - Device name
    - Booth ID
    - Booth name
    - Attendee data
    - Note
    - Tags
  - entity: event
    effect: reads
    facts:
    - Shared attendee data
  - entity: organization-profile
    effect: reads
    facts:
    - Name
    - Booth ID
    - Booth name
  contexts:
    api:
      place: exhibitor-api
- text: The Product returns the lead with its attendee details, or only its note and tags when the organization may not view collected leads
  kind: product
  actor: lead-scanning-app
  entities:
  - entity: lead
    effect: reads
    facts:
    - Attendee data
    - Note
    - Tags
  - entity: organization-profile
    effect: reads
    facts:
    - Lead access
  contexts:
    api:
      place: exhibitor-api
---

# Scan an attendee

## Trigger

Booth staff scan an attendee's badge.

## Outcome

The lead is kept with the shared attendee details, which the app shows.
