---
kind: primary
routes:
  web: Web
steps:
- text: The Applicant follows the confirmation link and is shown the request to confirm
  kind: actor
  actor: applicant
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
  contexts:
    web:
      place: event-website::signed-in::participation-confirmation
- text: The Applicant chooses Confirm
  kind: actor
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::signed-in::participation-confirmation
- text: The Product confirms the request if it is still accepted
  kind: product
  actor: applicant
  entities:
  - entity: exhibition-request
    effect: changes
    from: Accepted
    to: Confirmed
    facts:
    - Last updated
  contexts:
    web:
      place: event-website::signed-in::participation-confirmation
- text: The Product thanks the applicant and shows their requests
  kind: product
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::signed-in::my-requests
---

# Confirm through the acceptance email

## Trigger

An applicant follows the confirmation link in their acceptance email.

## Outcome

The request is confirmed and the applicant is thanked.

## Edge cases

- Opening the link confirms nothing by itself.
- Confirming an already confirmed request only says it was already confirmed.
