---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer chooses Publish all approved and reads the profiles that will be published
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
- text: The Organizer confirms
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organizations
- text: The Product publishes every active unpublished profile of the list
  kind: product
  actor: organizer
  entities:
  - entity: organization-profile
    effect: changes
    from: Unpublished
    to: Published
    facts: []
  contexts:
    web:
      place: organizer-backend::organizations
---

# Publish every approved profile

## Trigger

An organizer is ready to reveal the exhibition and chooses Publish all approved.

## Outcome

Every active unpublished profile of the list is public.
