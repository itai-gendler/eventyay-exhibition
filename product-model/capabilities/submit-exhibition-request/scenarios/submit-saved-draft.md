---
kind: alternative
routes:
  web: Web
steps:
- text: The Applicant completes the draft and chooses Submit request
  kind: actor
  actor: applicant
  entities:
  - entity: exhibition-request
    effect: changes
    from: Draft
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
    - Submitted at
  contexts:
    web:
      place: event-website::signed-in::request-form
- text: The Product sends the confirmation email and notifies the reviewing teams
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
---

# Submit a saved draft

## Trigger

An applicant opens a draft from their requests and chooses Submit request.

## Outcome

The draft becomes a submitted request, with the same confirmation and notification as a new one.
