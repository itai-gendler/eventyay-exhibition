---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer selects organization profiles and chooses Publish selected
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
- text: The Product publishes each selected active profile that is not published yet and reports how many are now visible
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

# Publish the selected profiles

## Trigger

An organizer selects exhibitors on the list and chooses Publish selected.

## Outcome

The selected active profiles are on the public website.

## Edge cases

- When nothing changes, the organizer is told the selected organizations already had that status.
