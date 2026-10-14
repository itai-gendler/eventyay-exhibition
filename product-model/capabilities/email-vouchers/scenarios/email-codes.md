---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer enters how many more vouchers to take and chooses Assign and prepare email
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organization-vouchers
- text: The Product takes the codes from the pool
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
  contexts:
    web:
      place: organizer-backend::organization-vouchers
- text: The Product places the voucher email listing the codes, with the CSV attachment, in the outbox
  kind: product
  actor: organizer
  entities:
  - entity: queued-email
    effect: creates
    to: In outbox
    facts:
    - Kind
    - Recipient
    - Subject
    - Body
    - Language
    - Attachment
  - entity: event
    effect: reads
    facts:
    - Attach voucher list
  - entity: organization-profile
    effect: reads
    facts:
    - Email
  contexts:
    web:
      place: organizer-backend::organization-vouchers
---

# Prepare the voucher email

## Trigger

An organizer chooses Assign and prepare email on an organization's Vouchers.

## Outcome

An email with every code the organization holds, and a CSV of them if the event attaches one, waits in the outbox.

## Edge cases

- The email lists the first five codes and refers to the CSV for the rest when the CSV is attached.
- Entering 0 emails the codes the organization already holds.
