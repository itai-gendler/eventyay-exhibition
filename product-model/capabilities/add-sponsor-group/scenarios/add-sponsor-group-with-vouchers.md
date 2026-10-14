---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer enters the group's name and vouchers per sponsor and saves
  kind: actor
  actor: organizer
  entities:
  - entity: sponsor-group
    effect: creates
    facts:
    - Name
    - Level
    - Show on front page
    - Vouchers per sponsor
  contexts:
    web:
      place: organizer-backend::sponsor-settings
- text: The Product says the group was added
  kind: product
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::sponsor-settings
---

# Add a group

## Trigger

An organizer opens Exhibition settings and Sponsors and chooses Add a Group.

## Outcome

The group is listed at the next level unless one was entered.
