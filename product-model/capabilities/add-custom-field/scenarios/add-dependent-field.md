---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer enters the question, picks the field it depends on and the values that show it, and saves
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
---

# Add a field shown only for some answers

## Trigger

An organizer asks for power requirements only from applicants who said they need power.

## Outcome

The new field appears on the form only while the chosen field has one of the chosen values.

## Edge cases

- Only checkbox and choice fields can be depended on.
