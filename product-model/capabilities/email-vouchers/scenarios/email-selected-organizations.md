---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer selects organization profiles and chooses Send vouchers to selected
  kind: actor
  actor: organizer
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: organizer-backend::organizations
- text: The Product shows who will get an email and who is skipped for having no email, a voucher count of 0, or a pool too small
  kind: product
  actor: organizer
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
    - Email
  - entity: sponsor-group
    effect: reads
    facts:
    - Vouchers per sponsor
  contexts:
    web:
      place: organizer-backend::organizations
- text: The Organizer confirms
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organizations
- text: The Product gives organizations without codes their default number from the pool and places a voucher email for each in the outbox
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
  contexts:
    web:
      place: organizer-backend::organizations
---

# Send vouchers to the selected organizations

## Trigger

An organizer selects exhibitors on the list and chooses Send vouchers to selected.

## Outcome

Each selected organization that can be sent to has a voucher email in the outbox; the others are named with the reason.
