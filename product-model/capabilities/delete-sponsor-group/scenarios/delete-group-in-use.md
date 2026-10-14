---
kind: validation
routes:
  web: Web
steps:
- text: The Organizer chooses to delete the group
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::sponsor-settings
- text: Organization profiles belong to the group
  kind: condition
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Sponsor group
  contexts:
    web:
      place: organizer-backend::sponsor-settings
- text: The Product says it cannot be deleted while it is assigned to organizations
  kind: product
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::sponsor-settings
---

# A group in use cannot be deleted

## Trigger

An organizer tries to delete a sponsor group that organizations belong to.

## Outcome

Nothing is deleted; the organizer is told why.
