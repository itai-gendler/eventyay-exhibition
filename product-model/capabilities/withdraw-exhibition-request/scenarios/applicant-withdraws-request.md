---
kind: primary
routes:
  web: Web
steps:
- text: The Applicant chooses Withdraw and confirms
  kind: actor
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::signed-in::my-requests
- text: The Product withdraws the request
  kind: product
  actor: applicant
  entities:
  - entity: exhibition-request
    effect: changes
    from: Accepted
    to: Withdrawn
    facts:
    - Last updated
  contexts:
    web:
      place: event-website::signed-in::my-requests
- text: The Product makes the organization profile inactive and takes it off the public site
  kind: product
  actor: applicant
  entities:
  - entity: organization-profile
    effect: changes
    from: Published
    to: Inactive
    facts: []
  contexts:
    web:
      place: event-website::signed-in::my-requests
- text: The Product emails the reviewing teams that the request was withdrawn
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

# Withdraw my accepted request

## Trigger

An applicant can no longer take part and chooses Withdraw on their accepted request.

## Outcome

The request is withdrawn, the organization profile is hidden, and the request managers and reviewers are notified.
