---
kind: alternative
routes:
  web: Web
steps:
- text: The Order viewer filters by publication, activity, sponsor group, lead scanning, lead access and voucher access, and searches by name, booth or email
  kind: actor
  actor: order-viewer
  entities:
  - entity: sponsor-group
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: organizer-backend::organizations
- text: The Product lists the matching organization profiles
  kind: product
  actor: order-viewer
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
    - Email
    - Booth ID
    - Booth name
    - Lead scanning
    - Lead access
    - Voucher access
    - Sponsor group
  contexts:
    web:
      place: organizer-backend::organizations
- text: The Order viewer reads the matching organization profiles
  kind: actor
  actor: order-viewer
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
    - Booth ID
    - Booth name
  contexts:
    web:
      place: organizer-backend::organizations
---

# Filter the lists

## Trigger

An order viewer looks for the published exhibitors that may scan leads.

## Outcome

Only matching organization profiles are listed.

## Edge cases

- Order viewers see no publish, voucher or download actions.
