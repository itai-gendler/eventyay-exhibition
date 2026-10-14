---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer selects organization profiles and chooses Unpublish selected
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
- text: The Product unpublishes them and reports how many were removed
  kind: product
  actor: organizer
  entities:
  - entity: organization-profile
    effect: changes
    from: Published
    to: Unpublished
    facts: []
  contexts:
    web:
      place: organizer-backend::organizations
---

# Unpublish the selected profiles

## Trigger

An organizer selects published profiles and chooses Unpublish selected.

## Outcome

The profiles are no longer on the public website.
