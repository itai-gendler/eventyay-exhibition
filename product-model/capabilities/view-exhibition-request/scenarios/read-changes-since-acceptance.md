---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer opens the edited request
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::request-review
- text: The Product compares the request's own fields and answers with how they were at acceptance
  kind: product
  actor: organizer
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Profile at acceptance
    - Edited after acceptance
    - Description
    - Answers
  contexts:
    web:
      place: organizer-backend::request-review
- text: The Organizer reads the changed fields with their old and new values
  kind: actor
  actor: organizer
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Profile at acceptance
    - Edited after acceptance
  contexts:
    web:
      place: organizer-backend::request-review
---

# See what changed since acceptance

## Trigger

An organizer opens a request the applicant edited after it was accepted.

## Outcome

The organizer sees each changed field with its value before acceptance and after the edit.
