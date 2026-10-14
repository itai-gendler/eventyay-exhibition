---
kind: validation
routes:
  web: Web
steps:
- text: The Organizer saves the form with neither exhibitor nor sponsor marked
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organization-editor
- text: The organization profile would be neither an exhibitor nor a sponsor
  kind: condition
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Exhibitor
    - Sponsor
  contexts:
    web:
      place: organizer-backend::organization-editor
- text: The Product keeps the form open with the error
  kind: product
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organization-editor
---

# A profile must be an exhibitor, a sponsor or both

## Trigger

An organizer adds an organization from the combined form without marking it as either.

## Outcome

Nothing is created; the form asks for a type.

## Edge cases

- Slides that are not a PDF and a missing required field are refused the same way.
