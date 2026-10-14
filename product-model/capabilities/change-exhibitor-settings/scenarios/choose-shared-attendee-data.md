---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer ticks the attendee details to share and saves
  kind: actor
  actor: organizer
  entities:
  - entity: event
    effect: changes
    facts:
    - Shared attendee data
  contexts:
    web:
      place: organizer-backend::exhibitor-settings
- text: The Product records the change and says the settings have been saved
  kind: product
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::exhibitor-settings
---

# Choose the shared attendee data

## Trigger

An organizer opens Exhibition settings and Exhibitors.

## Outcome

Exhibitors receive only the chosen attendee details from then on.

## Edge cases

- Leads already scanned keep the details they were taken with.
