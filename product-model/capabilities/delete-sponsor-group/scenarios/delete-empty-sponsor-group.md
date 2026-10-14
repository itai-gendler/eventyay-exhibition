---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer confirms deleting the sponsor group
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
- text: The Product deletes it and says so
  kind: product
  actor: organizer
  entities:
  - entity: sponsor-group
    effect: removes
  contexts:
    web:
      place: organizer-backend::sponsor-settings
---

# Delete an empty group

## Trigger

An organizer deletes an unused sponsor group.

## Outcome

The group is gone.
