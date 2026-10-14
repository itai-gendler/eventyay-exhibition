---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer reads the codes the organization holds and how many its pool has left
  kind: actor
  actor: organizer
  entities:
  - entity: voucher
    effect: reads
    facts:
    - Code
    - Product
    - Redeemed
  contexts:
    web:
      place: organizer-backend::organization-vouchers
- text: The Organizer enters how many vouchers to take from the pool and chooses Assign without emailing
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organization-vouchers
- text: The Product links that many unassigned codes of the organization's pool to it
  kind: product
  actor: organizer
  entities:
  - entity: voucher
    effect: creates
    facts:
    - Code
    - Product
    - Price effect
    - Value
    - Valid until
    - Maximum usages
    - Redeemed
    - Redeem link
    - Assigned at
  - entity: event
    effect: reads
    facts:
    - Exhibitor voucher pool
    - Sponsor voucher pool
  contexts:
    web:
      place: organizer-backend::organization-vouchers
---

# Take codes from the pool

## Trigger

An organizer opens an organization's Vouchers and chooses Assign without emailing.

## Outcome

The organization holds that many more codes from its pool.

## Edge cases

- Sponsor-only organizations draw from the sponsor pool when one is set; the default number comes from their sponsor group, else the event.
