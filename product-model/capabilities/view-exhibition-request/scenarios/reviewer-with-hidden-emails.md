---
kind: alternative
routes:
  web: Web
steps:
- text: The Request reviewer opens the request
  kind: actor
  actor: request-reviewer
  entities: []
  contexts:
    web:
      place: organizer-backend::request-review
- text: Every reviewer team of the person hides email addresses
  kind: condition
  entities:
  - entity: request-reviewer
    effect: reads
    facts:
    - Hide applicant emails
  contexts:
    web:
      place: organizer-backend::request-review
- text: The Request reviewer reads the request with the email addresses hidden
  kind: actor
  actor: request-reviewer
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
    - Description
    - Answers
    - Internal review notes
  - entity: account
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: organizer-backend::request-review
---

# A reviewer whose team hides applicant emails

## Trigger

A request reviewer whose teams hide applicant emails opens a request.

## Outcome

The reviewer reads the request without the applicant's email addresses or its history.
