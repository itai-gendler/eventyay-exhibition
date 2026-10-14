---
kind: validation
routes:
  api: API
steps:
- text: The Lead scanning app sends a key
  kind: actor
  actor: lead-scanning-app
  entities: []
  contexts:
    api:
      place: exhibitor-api
- text: No organization profile has that access key
  kind: condition
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Access key
  contexts:
    api:
      place: exhibitor-api
- text: The Product answers that the credentials are invalid
  kind: product
  actor: lead-scanning-app
  entities: []
  contexts:
    api:
      place: exhibitor-api
---

# An unknown key

## Trigger

The app sends a key no organization has, or none.

## Outcome

The app is told the credentials are invalid, or that parameters are missing.
