---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer confirms deleting the custom email template
  kind: actor
  actor: organizer
  entities:
  - entity: custom-email-template
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: organizer-backend::email-templates
- text: The Product deletes it and says so
  kind: product
  actor: organizer
  entities:
  - entity: custom-email-template
    effect: removes
  contexts:
    web:
      place: organizer-backend::email-templates
---

# Delete a template

## Trigger

An organizer deletes a template no longer used.

## Outcome

The template is gone; emails written from it are unaffected.
