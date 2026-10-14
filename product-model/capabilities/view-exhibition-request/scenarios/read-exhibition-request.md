---
kind: primary
routes:
  web: Web
steps:
- text: The Request manager opens the request
  kind: actor
  actor: request-manager
  entities: []
  contexts:
    web:
      place: organizer-backend::request-review
- text: The Request manager reads the details, answers, emails and history of the exhibition request
  kind: actor
  actor: request-manager
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
    - Internal review notes
  - entity: account
    effect: reads
    facts:
    - Name
    - Email
  - entity: queued-email
    effect: reads
    facts:
    - Subject
    - Recipient
    - Sent at
    - Send at
  - entity: request-history
    effect: reads
    facts:
    - Who
    - What happened
    - From state
    - To state
    - When
  contexts:
    web:
      place: organizer-backend::request-review
---

# Read a request

## Trigger

A request manager opens a request from the list or from a notification email.

## Outcome

The manager has everything the applicant sent and everything that happened to it.
