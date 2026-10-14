---
kind: validation
routes:
  web: Web
steps:
- text: The Organizer asks for vouchers
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organization-vouchers
- text: The pool has fewer unassigned codes than asked for, or no pool is chosen
  kind: condition
  entities:
  - entity: event
    effect: reads
    facts:
    - Exhibitor voucher pool
  contexts:
    web:
      place: organizer-backend::organization-vouchers
- text: The Product refuses and says how many codes the pool has left
  kind: product
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organization-vouchers
---

# The pool is too small

## Trigger

An organizer asks for more codes than the pool has left.

## Outcome

No code is taken; the organizer is told how many are left, or that no pool is chosen yet.
