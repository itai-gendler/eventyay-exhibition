---
kind: alternative
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
- text: The Product returns the CSV of the unredeemed codes
  kind: product
  actor: exhibitor-contact
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
      place: event-website::signed-in::my-vouchers
---

# Download my open codes

## Trigger

An exhibitor contact chooses Download CSV on the Open tab.

## Outcome

The contact has a CSV of the codes still to hand out.
