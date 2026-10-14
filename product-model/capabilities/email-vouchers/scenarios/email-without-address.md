---
kind: validation
routes:
  web: Web
steps:
- text: The Organizer chooses Assign and prepare email
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organization-vouchers
- text: The organization profile has no email and no request to fall back on
  kind: condition
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Email
  contexts:
    web:
      place: organizer-backend::organization-vouchers
- text: The Product says vouchers cannot be emailed
  kind: product
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organization-vouchers
---

# No email address

## Trigger

An organizer prepares a voucher email for an organization without an email address.

## Outcome

Nothing is queued; the organizer is told.

## Edge cases

- An organization holding no codes after the request is told there is nothing to email.
