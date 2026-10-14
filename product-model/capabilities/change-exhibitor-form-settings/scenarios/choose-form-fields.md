---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer reads the fields with their state and number of answers
  kind: actor
  actor: organizer
  entities:
  - entity: event
    effect: reads
    facts:
    - Standard fields
  - entity: custom-field
    effect: reads
    facts:
    - Question
    - Active
    - Required
  contexts:
    web:
      place: organizer-backend::exhibitor-form
- text: The Organizer turns fields on or off, marks some required and saves
  kind: actor
  actor: organizer
  entities:
  - entity: event
    effect: changes
    facts:
    - Standard fields
  - entity: custom-field
    effect: changes
    facts:
    - Active
    - Required
  contexts:
    web:
      place: organizer-backend::exhibitor-form
- text: The Product keeps the organization name, logo and banner asked and required, makes inactive fields optional, and says the form settings are saved
  kind: product
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::exhibitor-form
---

# Choose the asked and required fields

## Trigger

An organizer opens Exhibitor form and adjusts the fields.

## Outcome

The form asks the chosen fields; the list shows how many requests answered each.
