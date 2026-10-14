---
kind: validation
routes:
  web: Web
steps:
- text: The Organizer selects the profile and chooses Publish selected
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organizations
- text: The organization profile is inactive
  kind: condition
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: organizer-backend::organizations
- text: The Product says nothing changed
  kind: product
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organizations
---

# An inactive profile is not published

## Trigger

An organizer selects a profile whose request was withdrawn and chooses Publish selected.

## Outcome

The profile stays off the public website.
