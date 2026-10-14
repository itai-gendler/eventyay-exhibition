---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer changes the sponsor group's name and vouchers per sponsor and saves
  kind: actor
  actor: organizer
  entities:
  - entity: sponsor-group
    effect: changes
    facts:
    - Name
    - Vouchers per sponsor
  contexts:
    web:
      place: organizer-backend::sponsor-settings
---

# Rename a group

## Trigger

An organizer renames a sponsor group.

## Outcome

The new name shows wherever the group appears.
