---
kind: validation
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
- text: The organization profile may not scan leads
  kind: condition
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Lead scanning
  contexts:
    api:
      place: exhibitor-api
- text: The Product refuses, saying lead scanning is not enabled for the exhibitor
  kind: product
  actor: lead-scanning-app
  entities: []
  contexts:
    api:
      place: exhibitor-api
---

# Scanning is not allowed

## Trigger

The app scans for an organization whose lead scanning is off, or the badge is unknown.

## Outcome

No lead is made; the app is told why.

## Edge cases

- An unknown attendee is answered as not found; a missing value as missing parameters.
