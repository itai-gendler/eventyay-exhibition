---
kind: alternative
routes:
  web: Web
steps:
- text: The Applicant opens the request form after following the secret link
  kind: actor
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::signed-in::request-form
- text: The call is enabled and private and they used its current secret link
  kind: condition
  entities:
  - entity: event
    effect: reads
    facts:
    - Call enabled
    - Private call
    - Secret call link
  contexts:
    web:
      place: event-website::signed-in::request-form
- text: The Applicant fills in the form and chooses Submit request
  kind: actor
  actor: applicant
  entities:
  - entity: exhibition-request
    effect: creates
    to: Submitted
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
    - Code
    - Exhibitor
    - Sponsor
    - Last updated
    - Submitted at
  contexts:
    web:
      place: event-website::signed-in::request-form
---

# Submit late through the secret link

## Trigger

An applicant invited with the secret link submits after the public deadline.

## Outcome

The request is submitted as on an open call.
