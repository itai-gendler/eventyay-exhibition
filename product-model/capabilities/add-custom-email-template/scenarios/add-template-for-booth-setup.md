---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer enters a name, subject and body and saves
  kind: actor
  actor: organizer
  entities:
  - entity: custom-email-template
    effect: creates
    facts:
    - Name
    - Subject
    - Body
  contexts:
    web:
      place: organizer-backend::custom-template-editor
- text: The Product says the template was created and shows the templates
  kind: product
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::email-templates
---

# Add a template

## Trigger

An organizer adds a template for the booth setup instructions.

## Outcome

The template is offered when composing and can be reworded with the other templates.
