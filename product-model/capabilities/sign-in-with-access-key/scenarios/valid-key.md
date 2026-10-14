---
kind: primary
routes:
  api: API
steps:
- text: The Lead scanning app sends the access key
  kind: actor
  actor: lead-scanning-app
  entities: []
  contexts:
    api:
      place: exhibitor-api
- text: The Product answers with the organization profile's name, booth ID and booth name
  kind: product
  actor: lead-scanning-app
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Access key
    - Name
    - Booth ID
    - Booth name
  contexts:
    api:
      place: exhibitor-api
---

# Sign in with a valid key

## Trigger

The exhibitor's staff enter the access key from the access email into the app.

## Outcome

The app knows which organization and booth it scans for.
