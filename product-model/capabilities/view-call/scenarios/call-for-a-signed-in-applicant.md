---
kind: alternative
routes:
  web: Web
steps:
- text: The Applicant opens the call
  kind: actor
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::call-page
- text: The Product shows the call with Submit a request, and View your requests for their exhibition requests
  kind: product
  actor: applicant
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
  contexts:
    web:
      place: event-website::call-page
- text: The Applicant reads the call
  kind: actor
  actor: applicant
  entities:
  - entity: event
    effect: reads
    facts:
    - Call headline
    - Call text
    - Submission deadline
  contexts:
    web:
      place: event-website::call-page
---

# A logged-in applicant sees their requests

## Trigger

A logged-in applicant who has applied before opens the call.

## Outcome

The applicant can submit a new request or go to their requests.
