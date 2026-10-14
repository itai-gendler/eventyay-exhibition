---
kind: primary
routes:
  web: Web
steps:
- text: The Applicant enters at least the organization name and chooses to save as draft
  kind: actor
  actor: applicant
  entities:
  - entity: exhibition-request
    effect: creates
    to: Draft
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
  contexts:
    web:
      place: event-website::signed-in::request-form
- text: The Product says the request has been saved and shows the applicant's requests
  kind: product
  actor: applicant
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
  contexts:
    web:
      place: event-website::signed-in::my-requests
---

# Save a new request as a draft

## Trigger

An applicant fills in part of the form and chooses to save it as a draft for now.

## Outcome

A draft request exists; nobody is notified and it can be finished while the call is open.

## Edge cases

- Saving a draft without the organization name is refused.
