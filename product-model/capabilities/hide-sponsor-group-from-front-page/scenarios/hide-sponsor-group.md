---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer turns off Front Page for the sponsor group
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

# Hide a group

## Trigger

An organizer turns off Front Page for a sponsor group.

## Outcome

The group no longer appears on the front page.
