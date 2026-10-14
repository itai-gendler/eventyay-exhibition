---
kind: alternative
routes:
  web: Web
steps:
- text: The Request reviewer filters by state Submitted and searches by name
  kind: actor
  actor: request-reviewer
  entities: []
  contexts:
    web:
      place: organizer-backend::requests
- text: The Product lists the matching requests, searching the submitter's email only for those allowed to see it
  kind: product
  actor: request-reviewer
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
  - entity: account
    effect: reads
    facts:
    - Name
    - Email
  - entity: request-reviewer
    effect: reads
    facts:
    - Hide applicant emails
  contexts:
    web:
      place: organizer-backend::requests
- text: The Request reviewer reads the matching exhibition requests
  kind: actor
  actor: request-reviewer
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
    - Last updated
  contexts:
    web:
      place: organizer-backend::requests
---

# Search and filter requests

## Trigger

A request reviewer looks for the requests still waiting for a decision.

## Outcome

Only matching requests are listed; reviewers whose emails are hidden search by name only.

## Edge cases

- Reviewers see no decision buttons.
