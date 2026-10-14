---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer drags a sponsor group to a new place
  kind: actor
  actor: organizer
  entities:
  - entity: sponsor-group
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: organizer-backend::sponsor-settings
- text: The Product numbers every group's level from 1 in the new order
  kind: product
  actor: organizer
  entities:
  - entity: sponsor-group
    effect: changes
    facts:
    - Level
  contexts:
    web:
      place: organizer-backend::sponsor-settings
---

# Drag groups into order

## Trigger

An organizer moves Silver above Bronze.

## Outcome

The groups' levels follow the new order on the front page, the lists and the filters.
