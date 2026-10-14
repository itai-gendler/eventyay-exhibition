---
kind: alternative
routes:
  api: API
steps:
- text: The Lead scanning app asks for the redemptions with the access key
  kind: actor
  actor: lead-scanning-app
  entities: []
  contexts:
    api:
      place: exhibitor-api
- text: The access key belongs to an organization profile here that has voucher access
  kind: condition
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Access key
    - Voucher access
  contexts:
    api:
      place: exhibitor-api
- text: The Product returns each voucher redemption with its code, time, order status and the shared attendee details
  kind: product
  actor: lead-scanning-app
  entities:
  - entity: voucher-redemption
    effect: reads
    facts:
    - Voucher code
    - Redeemed on
    - Order status
    - Attendee data
  contexts:
    api:
      place: exhibitor-api
---

# The app fetches the redemptions

## Trigger

The lead scanning app asks for the organization's voucher redemptions with its access key.

## Outcome

The app receives each redemption with the shared attendee details.
