---
kind: alternative
routes:
  web: Web
steps:
- text: The Request reviewer writes internal review notes and chooses Save
  kind: actor
  actor: request-reviewer
  entities:
  - entity: exhibition-request
    effect: changes
    facts:
    - Internal review notes
  contexts:
    web:
      place: organizer-backend::request-review
---

# Keep internal notes

## Trigger

A request reviewer writes down their assessment.

## Outcome

The notes are saved on the request; the applicant never sees them.

## Edge cases

- Once a request is decided, only the notes can be changed on the review page.
