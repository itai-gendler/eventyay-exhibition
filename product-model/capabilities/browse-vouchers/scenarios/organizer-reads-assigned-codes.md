---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer opens the organization's vouchers
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organization-vouchers
- text: The Organizer reads each assigned voucher with its product, price effect, validity and redemptions
  kind: actor
  actor: organizer
  entities:
  - entity: voucher
    effect: reads
    facts:
    - Code
    - Product
    - Price effect
    - Valid until
    - Redeemed
  - entity: queued-email
    effect: reads
    facts:
    - Sent at
  contexts:
    web:
      place: organizer-backend::organization-vouchers
---

# Look at an organization's codes

## Trigger

An organizer opens an organization's Vouchers.

## Outcome

The organizer sees every code the organization holds and when its vouchers were last emailed.
