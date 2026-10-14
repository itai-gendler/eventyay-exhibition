---
kind: primary
routes:
  web: Web
steps:
- text: The Applicant chooses Reinstate and confirms
  kind: actor
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::signed-in::my-requests
- text: The Product makes the request submitted again
  kind: product
  actor: applicant
  entities:
  - entity: exhibition-request
    effect: changes
    from: Withdrawn
    to: Submitted
    facts:
    - Submitted at
    - Last updated
  contexts:
    web:
      place: event-website::signed-in::my-requests
- text: The Product emails the reviewing teams that the request was reinstated
  kind: product
  actor: applicant
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
    - Contact email
  contexts:
    web:
      place: event-website::signed-in::my-requests
---

# Reinstate a withdrawn request

## Trigger

An applicant chooses Reinstate on a withdrawn request and confirms.

## Outcome

The request is pending review again and the request managers and reviewers are notified.
