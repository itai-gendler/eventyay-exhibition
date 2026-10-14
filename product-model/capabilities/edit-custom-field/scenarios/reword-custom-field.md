---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer changes the question and removes an option, and saves
  kind: actor
  actor: organizer
  entities:
  - entity: custom-field
    as: edited
    effect: changes
    facts:
    - Question
    - Options
  contexts:
    web:
      place: organizer-backend::custom-field-editor
- text: The Product drops the removed option from the fields that depend on it, so a field left with no value stops being conditional
  kind: product
  actor: organizer
  entities:
  - entity: custom-field
    as: dependent
    effect: changes
    facts:
    - Depends on
  contexts:
    web:
      place: organizer-backend::custom-field-editor
---

# Change a field

## Trigger

An organizer rewords a question and removes one of its options.

## Outcome

The form asks the changed question; fields that depended on the removed option no longer depend on it.

## Edge cases

- Changing a field to a type without options removes its options.
