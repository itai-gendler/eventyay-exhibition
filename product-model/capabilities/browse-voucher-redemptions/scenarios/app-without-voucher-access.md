---
kind: validation
routes:
  api: API
steps:
- text: The Lead scanning app asks for the redemptions
  kind: actor
  actor: lead-scanning-app
  entities: []
  contexts:
    api:
      place: exhibitor-api
- text: The organization profile does not have voucher access
  kind: condition
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Voucher access
  contexts:
    api:
      place: exhibitor-api
- text: The Product refuses, saying the exhibitor may not see redemption data
  kind: product
  actor: lead-scanning-app
  entities: []
  contexts:
    api:
      place: exhibitor-api
---

# No voucher access

## Trigger

The app asks for redemptions of an organization without voucher access.

## Outcome

The app is refused; with an unknown key it is told the key is invalid.
