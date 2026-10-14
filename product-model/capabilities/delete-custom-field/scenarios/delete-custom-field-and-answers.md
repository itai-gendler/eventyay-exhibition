---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer reads which fields depend on the field and confirms the deletion
  kind: actor
  actor: organizer
  entities:
  - entity: custom-field
    as: deleted
    effect: reads
    facts:
    - Question
    - Depends on
  contexts:
    web:
      place: organizer-backend::custom-field-editor
- text: The Product clears the dependency of the fields that depended on it and deletes the field
  kind: product
  actor: organizer
  entities:
  - entity: custom-field
    as: deleted
    effect: removes
  - entity: custom-field
    as: dependent
    effect: changes
    facts:
    - Depends on
  - entity: exhibition-request
    effect: reads
    facts:
    - Answers
  contexts:
    web:
      place: organizer-backend::custom-field-editor
---

# Delete a field

## Trigger

An organizer no longer needs a question.

## Outcome

The field and its answers are gone; the fields that depended on it are no longer conditional.
