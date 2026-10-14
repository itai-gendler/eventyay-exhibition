---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer drags an organization profile to a new place
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
- text: The Product saves the position of every exhibitor in the new order
  kind: product
  actor: organizer
  entities:
  - entity: organization-profile
    effect: changes
    facts:
    - Position
  contexts:
    web:
      place: organizer-backend::organizations
---

# Drag exhibitors into order

## Trigger

An organizer moves an exhibitor to the top of the unfiltered list.

## Outcome

The Exhibition page lists the exhibitors in the new order.

## Edge cases

- Dragging is offered only on an unfiltered list that fits one page.
- Sponsors are ordered within their sponsor group.
