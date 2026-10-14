---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer confirms resetting the standard field
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::standard-field-editor
- text: The Product removes the field's own label and help text
  kind: product
  actor: organizer
  entities:
  - entity: event
    effect: changes
    facts:
    - Standard fields
  contexts:
    web:
      place: organizer-backend::standard-field-editor
---

# Reset a field

## Trigger

An organizer resets the relabelled banner field.

## Outcome

The field shows its default label and help text again.
