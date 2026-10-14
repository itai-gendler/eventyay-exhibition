---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer changes a custom field answer on the profile and saves
  kind: actor
  actor: organizer
  entities:
  - entity: exhibition-request
    effect: changes
    facts:
    - Answers
  - entity: custom-field
    effect: reads
    facts:
    - Question
  contexts:
    web:
      place: organizer-backend::organization-editor
---

# Change the answers of the request

## Trigger

An organizer corrects an answer the applicant gave on the form.

## Outcome

The request's answers change and the change is recorded in the request's history.
