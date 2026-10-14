---
kind: alternative
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
- text: The call is private and they have at least one request to it
  kind: condition
  entities:
  - entity: event
    effect: reads
    facts:
    - Private call
  - entity: exhibition-request
    effect: reads
    facts:
    - Code
  contexts:
    web:
      place: event-website::signed-in::my-requests
- text: The Applicant reads their exhibition requests
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

# Requests to a private call stay reachable

## Trigger

An applicant who applied to a private call opens their requests without the secret link.

## Outcome

Their requests are listed although the call itself stays hidden.

## Edge cases

- Someone without any request to a private call and without its link finds no such page.
