---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer drags a field to a new place
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::exhibitor-form
- text: The Product saves the order of all standard fields and custom fields
  kind: product
  actor: organizer
  entities:
  - entity: event
    effect: changes
    facts:
    - Standard fields
  - entity: custom-field
    effect: changes
    facts:
    - Position
  contexts:
    web:
      place: organizer-backend::exhibitor-form
---

# Drag fields into order

## Trigger

An organizer moves the banner field below a custom field.

## Outcome

The exhibitor form, the organization editor and the request form follow the new order.
