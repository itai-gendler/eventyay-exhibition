---
kind: primary
routes:
  web: Web
steps:
- text: The Applicant opens the request from their requests or from the link in its confirmation email
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
- text: The Applicant changes details and answers and chooses Save changes
  kind: actor
  actor: applicant
  entities:
  - entity: exhibition-request
    effect: changes
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
    - Last updated
  contexts:
    web:
      place: event-website::signed-in::request-form
- text: The Product says the changes have been saved and shows the applicant's requests
  kind: product
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::signed-in::my-requests
---

# Change a submitted request

## Trigger

An applicant opens a submitted request while the call is open and changes it.

## Outcome

The request keeps waiting for review with the new details; the change is recorded in its history.
