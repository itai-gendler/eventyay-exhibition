---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer turns on Front Page for the sponsor group
  kind: actor
  actor: organizer
  entities:
  - entity: sponsor-group
    effect: changes
    facts:
    - Show on front page
  contexts:
    web:
      place: organizer-backend::sponsor-settings
---

# Show a group

## Trigger

An organizer turns on Front Page for a sponsor group.

## Outcome

The group's published sponsors with a logo appear on the front page.
