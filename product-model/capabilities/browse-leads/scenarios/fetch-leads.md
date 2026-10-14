---
kind: primary
routes:
  api: API
steps:
- text: The Lead scanning app asks for the leads with the access key
  kind: actor
  actor: lead-scanning-app
  entities: []
  contexts:
    api:
      place: exhibitor-api
- text: The organization profile may view collected leads
  kind: condition
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Lead access
  contexts:
    api:
      place: exhibitor-api
- text: The Product returns every lead of the organization
  kind: product
  actor: lead-scanning-app
  entities:
  - entity: lead
    effect: reads
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
  contexts:
    api:
      place: exhibitor-api
---

# Fetch the leads

## Trigger

Booth staff open the list of leads in the app.

## Outcome

The app has every lead with its attendee details, note and tags.
