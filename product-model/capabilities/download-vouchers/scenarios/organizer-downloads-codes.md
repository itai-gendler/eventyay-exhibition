---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Download codes
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organization-vouchers
- text: The Product returns the CSV of the codes
  kind: product
  actor: organizer
  entities:
  - entity: voucher
    effect: reads
    facts:
    - Code
    - Redeem link
    - Product
    - Price effect
    - Value
    - Valid until
    - Redeemed
    - Maximum usages
  contexts:
    web:
      place: organizer-backend::organization-vouchers
---

# Download an organization's codes

## Trigger

An organizer chooses Download codes (CSV) on an organization's Vouchers.

## Outcome

The organizer has a CSV of every code with its redeem link, product, price effect, value, validity, redemptions and usages.
