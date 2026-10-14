---
kind: validation
routes:
  web: Web
steps:
- text: The Organizer chooses Return to pool on a code
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organization-vouchers
- text: The code was redeemed, or a voucher email to the organization went out after it was assigned
  kind: condition
  entities:
  - entity: voucher
    effect: reads
    facts:
    - Redeemed
    - Assigned at
  - entity: queued-email
    effect: reads
    facts:
    - Kind
  contexts:
    web:
      place: organizer-backend::organization-vouchers
- text: The Product refuses and says why
  kind: product
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organization-vouchers
---

# A redeemed or emailed code cannot be returned

## Trigger

An organizer tries to return a code that was redeemed or already sent in a voucher email.

## Outcome

The code stays with the organization; the organizer is told to delete it in the ticket shop instead.
