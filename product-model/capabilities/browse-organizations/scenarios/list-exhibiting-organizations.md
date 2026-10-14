---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer opens Exhibitors
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organizations
- text: The Product lists the exhibiting profiles in their order, with when their vouchers were last emailed or whether a voucher email waits in the outbox
  kind: product
  actor: organizer
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Exhibitor
    - Position
  - entity: queued-email
    effect: reads
    facts:
    - Kind
    - Sent at
  contexts:
    web:
      place: organizer-backend::organizations
- text: The Organizer reads each organization profile's name, booth and access key
  kind: actor
  actor: organizer
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
    - Booth ID
    - Booth name
    - Access key
    - Sponsor group
  contexts:
    web:
      place: organizer-backend::organizations
---

# Look through the exhibitors

## Trigger

An organizer opens Exhibitors.

## Outcome

The organizer sees each exhibitor's name, booth, whether it is published and whether its vouchers were emailed.

## Edge cases

- The Sponsors list shows the sponsors under their sponsor groups by level, then those without a group.
