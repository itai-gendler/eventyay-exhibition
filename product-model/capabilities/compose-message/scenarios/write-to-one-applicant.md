---
kind: alternative
routes:
  web: Web
steps:
- text: The Request reviewer chooses Send email and edits the prefilled message
  kind: actor
  actor: request-reviewer
  entities:
  - entity: event
    effect: reads
    facts:
    - Email templates
  contexts:
    web:
      place: organizer-backend::compose
- text: The Product writes the email to the request's contact address and notes it in its history
  kind: product
  actor: request-reviewer
  entities:
  - entity: queued-email
    effect: creates
    to: In outbox
    facts:
    - Kind
    - Recipient
    - Subject
    - Body
    - Language
  - entity: exhibition-request
    effect: reads
    facts:
    - Contact email
    - Organization name
  contexts:
    web:
      place: organizer-backend::compose
- text: The Product shows the request's review page
  kind: product
  actor: request-reviewer
  entities: []
  contexts:
    web:
      place: organizer-backend::request-review
---

# Ask one applicant for more information

## Trigger

A request reviewer chooses Send email on a request's review page.

## Outcome

The email, prefilled from the Request more information template, is sent or queued and noted in the request's history; the reviewer is back on the review page.

## Edge cases

- A reviewer whose emails are hidden does not see the applicant's address.
