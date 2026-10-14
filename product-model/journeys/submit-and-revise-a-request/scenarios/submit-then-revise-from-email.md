---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The Applicant fills in the form and chooses Submit request
  kind: actor
  actor: applicant
  capability: submit-exhibition-request
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
- text: The Product sends the confirmation email with a link to the request
  kind: product
  actor: applicant
  capability: submit-exhibition-request
  entities:
  - entity: queued-email
    effect: creates
    to: Sent
    facts:
    - Kind
    - Recipient
    - Subject
    - Body
    - Language
    - Sent at
  contexts:
    web:
      place: event-website::signed-in::request-form
- text: The Applicant follows the link in the email and corrects the description
  kind: actor
  actor: applicant
  capability: edit-exhibition-request
  entities:
  - entity: exhibition-request
    effect: changes
    facts:
    - Description
    - Last updated
  contexts:
    web:
      place: event-website::signed-in::request-form
---

# Revise a request through the confirmation email

## Trigger

An applicant submits a request on an open call.

## Outcome

The request is still submitted, with the corrected details.
