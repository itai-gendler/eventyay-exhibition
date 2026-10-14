---
kind: primary
routes:
  web: Web
steps:
- text: The Exhibitor contact opens the vouchers of their organization
  kind: actor
  actor: exhibitor-contact
  entities: []
  contexts:
    web:
      place: event-website::signed-in::my-vouchers
- text: The Product lists the redemptions of the organization's codes in orders that were not cancelled
  kind: product
  actor: exhibitor-contact
  entities:
  - entity: event
    effect: reads
    facts:
    - Shared attendee data
  contexts:
    web:
      place: event-website::signed-in::my-vouchers
- text: The Exhibitor contact reads each voucher redemption
  kind: actor
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

# See who redeemed my vouchers

## Trigger

An exhibitor contact opens their organization's vouchers in My Exhibitions.

## Outcome

The contact sees each redemption with the shared attendee details, the order and when it was placed, and how many codes were issued and redeemed.
