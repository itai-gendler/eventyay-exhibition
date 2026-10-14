---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer enters the question, picks Dropdown, enters the options and saves
  kind: actor
  actor: organizer
  entities:
  - entity: custom-field
    effect: creates
    facts:
    - Question
    - Type
    - Help text
    - Options
    - Required
    - Active
    - Position
    - Depends on
  contexts:
    web:
      place: organizer-backend::custom-field-editor
- text: The Product places the field after every existing field and shows the exhibitor form
  kind: product
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::exhibitor-form
---

# Add a choice field

## Trigger

An organizer wants applicants to choose their booth size.

## Outcome

The form asks the new question last, with its options.
