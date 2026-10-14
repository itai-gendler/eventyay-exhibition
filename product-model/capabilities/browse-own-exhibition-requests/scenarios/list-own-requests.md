---
kind: primary
routes:
  web: Web
steps:
- text: The Applicant opens their requests
  kind: actor
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::signed-in::my-requests
- text: The Product lists the applicant's requests with Edit while they can still be changed and View otherwise
  kind: product
  actor: applicant
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
    - Last updated
  - entity: event
    effect: reads
    facts:
    - Call open
  contexts:
    web:
      place: event-website::signed-in::my-requests
- text: The Applicant reads the name, state and last change of each exhibition request
  kind: actor
  actor: applicant
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
    - Last updated
  contexts:
    web:
      place: event-website::signed-in::my-requests
---

# See my requests

## Trigger

An applicant chooses Exhibition requests in the account menu of an event they applied to.

## Outcome

The applicant sees each of their requests with its state and what they can do with it.
