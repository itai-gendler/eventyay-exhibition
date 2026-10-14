---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer changes the profile's details, sessions and settings and saves
  kind: actor
  actor: organizer
  entities:
  - entity: organization-profile
    effect: changes
    facts:
    - Description
    - Logo
    - Related sessions
    - Lead access
    - Lead scanning behavior
  contexts:
    web:
      place: organizer-backend::organization-editor
- text: The Product records the changed fields and shows the list the profile was opened from
  kind: product
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organizations
---

# Edit a profile

## Trigger

An organizer opens an exhibitor's profile from the list and changes it.

## Outcome

The profile shows the changes; the organizer is back on the list it came from.
