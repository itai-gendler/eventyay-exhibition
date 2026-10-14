---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer enters a label and help text for the standard field and saves
  kind: actor
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

# Relabel a standard field

## Trigger

An organizer wants the banner field to explain the expected size.

## Outcome

The request form and the organization editor show the new label and help text.

## Edge cases

- An empty label keeps the default one.
