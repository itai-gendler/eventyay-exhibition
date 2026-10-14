---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Return to pool on a code
  kind: actor
  actor: organizer
  entities:
  - entity: voucher
    effect: reads
    facts:
    - Code
  contexts:
    web:
      place: organizer-backend::organization-vouchers
- text: The Product unlinks the code from the organization
  kind: product
  actor: organizer
  entities:
  - entity: voucher
    effect: removes
  contexts:
    web:
      place: organizer-backend::organization-vouchers
---

# Return a code

## Trigger

An organizer gave an organization one code too many.

## Outcome

The code is back in the pool; it still exists in the ticket shop.
