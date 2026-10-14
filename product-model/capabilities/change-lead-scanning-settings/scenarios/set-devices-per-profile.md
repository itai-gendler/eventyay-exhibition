---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer enters the devices per profile and saves
  kind: actor
  actor: organizer
  entities:
  - entity: event
    effect: changes
    facts:
    - Devices per profile
  contexts:
    web:
      place: organizer-backend::lead-scanning-settings
---

# Set the devices per profile

## Trigger

An organizer opens Exhibition settings and Lead scanning.

## Outcome

Profiles that get lead scanning from now on receive that many devices.

## Edge cases

- More than 50 is refused; 0 means devices are only added by hand.
