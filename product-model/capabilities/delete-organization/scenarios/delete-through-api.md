---
kind: alternative
routes:
  api: API
steps:
- text: The Organizer asks the organizer API to delete the profile
  kind: actor
  actor: organizer
  entities:
  - entity: organization-profile
    effect: removes
    from: Published
  contexts:
    api:
      place: organizer-api
---

# Delete a profile through the organizer API

## Trigger

An integration of the organizers deletes a profile.

## Outcome

The profile is gone as when deleted in the back office.
