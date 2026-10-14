---
kind: validation
routes:
  web: Web
steps:
- text: The Applicant opens the request
  kind: actor
  actor: applicant
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
    - Description
    - Language
    - Contact email
    - Website
    - Contact page URL
    - Video URL
    - Slides
    - Logo
    - Banner
    - Message to the organizers
    - Social media links
    - Extra links
    - Booth name
    - Answers
  contexts:
    web:
      place: event-website::signed-in::request-form
- text: The request is not accepted and the call is no longer open to them
  kind: condition
  entities:
  - entity: event
    effect: reads
    facts:
    - Call open
  contexts:
    web:
      place: event-website::signed-in::request-form
- text: The Product shows the request without a way to save it
  kind: product
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::signed-in::request-form
---

# The call has closed for an undecided request

## Trigger

An applicant opens a draft or submitted request after the call closed.

## Outcome

The request is shown read-only; saving is refused with a message that it can no longer be edited.

## Edge cases

- Rejected and withdrawn requests are always read-only.
