---
kind: primary
routes:
  web: Web
steps:
- text: The Exhibitor contact chooses Download CSV
  kind: actor
  actor: exhibitor-contact
  entities: []
  contexts:
    web:
      place: event-website::signed-in::my-vouchers
- text: The Product returns the CSV of the voucher redemptions
  kind: product
  actor: exhibitor-contact
  entities:
  - entity: voucher-redemption
    effect: reads
    facts:
    - Voucher code
    - Attendee data
    - Order
    - Order status
    - Redeemed on
  contexts:
    web:
      place: event-website::signed-in::my-vouchers
---

# Download the redemptions

## Trigger

An exhibitor contact chooses Download CSV on the redemptions.

## Outcome

The contact has a CSV of the redemptions with the shared attendee columns.
