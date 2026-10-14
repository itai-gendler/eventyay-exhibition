---
kind: alternative
routes:
  api: API
steps:
- text: The Organizer sends new social media links for the profile to the organizer API
  kind: actor
  actor: organizer
  entities:
  - entity: organization-profile
    effect: changes
    facts:
    - Social media links
  contexts:
    api:
      place: organizer-api
---

# Change a profile through the organizer API

## Trigger

An integration of the organizers updates an exhibitor's links.

## Outcome

The links are replaced by the ones sent.

## Edge cases

- Unknown social networks and slides links that are not a PDF are refused.
