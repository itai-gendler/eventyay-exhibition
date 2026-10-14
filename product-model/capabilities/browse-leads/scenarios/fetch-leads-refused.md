---
kind: validation
routes:
  api: API
steps:
- text: The Lead scanning app asks for the leads
  kind: actor
  actor: lead-scanning-app
  entities: []
  contexts:
    api:
      place: exhibitor-api
- text: The organization profile may not view collected leads
  kind: condition
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Lead access
  contexts:
    api:
      place: exhibitor-api
- text: The Product refuses, saying the exhibitor may not access collected lead data
  kind: product
  actor: lead-scanning-app
  entities: []
  contexts:
    api:
      place: exhibitor-api
---

# Viewing leads is not allowed

## Trigger

The app asks for the leads of an organization that may keep scanning but not view leads.

## Outcome

The app is refused.
