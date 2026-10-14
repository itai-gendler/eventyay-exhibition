---
kind: validation
routes:
  web: Web
steps:
- text: The Organizer saves the field
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::custom-field-editor
- text: A choice field has no option, or the dependency has no value, an unknown value, or leads back to the field itself
  kind: condition
  entities:
  - entity: custom-field
    effect: reads
    facts:
    - Type
    - Depends on
  contexts:
    web:
      place: organizer-backend::custom-field-editor
- text: The Product keeps the form open with the error
  kind: product
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::custom-field-editor
---

# A field the form cannot ask

## Trigger

An organizer saves a choice field without options, or a dependency that would loop.

## Outcome

Nothing is saved; the form says what is wrong.
