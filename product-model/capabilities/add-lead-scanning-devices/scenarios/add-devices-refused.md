---
kind: validation
routes:
  web: Web
steps:
- text: The Organizer chooses Add devices
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organization-devices
- text: Their team may not change the organizer settings
  kind: condition
  entities:
  - entity: organizer
    effect: reads
    facts:
    - Can change organizer settings
  contexts:
    web:
      place: organizer-backend::organization-devices
- text: The Product refuses the request
  kind: product
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organization-devices
---

# Adding devices needs the organizer settings permission

## Trigger

An organizer whose team may not change the organizer account's settings tries to add devices.

## Outcome

No device is created; the request is refused.
