---
kind: primary
routes:
  web: Web
steps:
- text: The Applicant opens the request form
  kind: actor
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::signed-in::request-form
- text: The Product shows the active standard fields and custom fields with their labels and help texts, in the configured order
  kind: product
  actor: applicant
  entities:
  - entity: event
    effect: reads
    facts:
    - Standard fields
    - Content languages
  - entity: custom-field
    effect: reads
    facts:
    - Question
    - Type
    - Help text
    - Options
    - Required
    - Active
    - Position
  contexts:
    web:
      place: event-website::signed-in::request-form
- text: The Applicant fills in the organization's details and answers and chooses Submit request
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
- text: The Product sends the applicant a confirmation email with a link to the request
  kind: product
  actor: applicant
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
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
    - Contact email
    - Code
  contexts:
    web:
      place: event-website::signed-in::request-form
- text: The Product emails the reviewing teams that a request was submitted, with the number of pending requests
  kind: product
  actor: applicant
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
    - Contact email
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

# Submit a new request

## Trigger

A logged-in applicant chooses Submit a request on an open call.

## Outcome

The request is submitted, the applicant has a confirmation email with a link to it, the organizers are notified, and the applicant lands on their requests.

## Edge cases

- When no team has request managers or reviewers, the teams that may change the event's settings are notified instead.
- Every new request is a request to exhibit; organizers decide at review whether it is also, or only, a sponsor.
