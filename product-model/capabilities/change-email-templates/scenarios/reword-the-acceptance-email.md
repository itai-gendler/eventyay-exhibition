---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer reads the templates with their placeholders
  kind: actor
  actor: organizer
  entities:
  - entity: event
    effect: reads
    facts:
    - Email templates
  contexts:
    web:
      place: organizer-backend::email-templates
- text: The Organizer rewrites the acceptance email's subject and body per language and the custom templates, and saves
  kind: actor
  actor: organizer
  entities:
  - entity: event
    effect: changes
    facts:
    - Email templates
  - entity: custom-email-template
    effect: changes
    facts:
    - Subject
    - Body
  contexts:
    web:
      place: organizer-backend::email-templates
- text: The Product says the templates have been saved
  kind: product
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::email-templates
---

# Reword the templates

## Trigger

An organizer opens Message center and Templates and rewrites the acceptance email.

## Outcome

Emails written from then on use the new wording; emails already in the outbox keep theirs.

## Edge cases

- A template left empty falls back to its default wording.
