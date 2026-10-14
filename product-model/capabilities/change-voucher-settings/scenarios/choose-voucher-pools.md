---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer reads how many codes each pool has left
  kind: actor
  actor: organizer
  entities:
  - entity: event
    effect: reads
    facts:
    - Exhibitor voucher pool
    - Sponsor voucher pool
  contexts:
    web:
      place: organizer-backend::voucher-settings
- text: The Organizer picks the exhibitor and sponsor pools, the number per organization and the CSV attachment, and saves
  kind: actor
  actor: organizer
  entities:
  - entity: event
    effect: changes
    facts:
    - Exhibitor voucher pool
    - Sponsor voucher pool
    - Vouchers per organization
    - Attach voucher list
  contexts:
    web:
      place: organizer-backend::voucher-settings
---

# Choose the pools and defaults

## Trigger

An organizer has created vouchers with a tag in the ticket shop and opens Exhibition settings and Vouchers.

## Outcome

Organizations draw from the chosen pools; the page shows how many unassigned codes each pool has left.

## Edge cases

- An empty sponsor pool means sponsors draw from the exhibitor pool.
