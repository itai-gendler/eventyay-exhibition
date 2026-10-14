---
kind: alternative
routes:
  web: Web
steps:
- text: The Applicant opens the front page
  kind: actor
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::front-page
- text: The Applicant reads the sponsor groups and their sponsors' logos
  kind: actor
  actor: applicant
  entities:
  - entity: sponsor-group
    effect: reads
    facts:
    - Name
  - entity: organization-profile
    effect: reads
    facts:
    - Name
    - Logo
  contexts:
    web:
      place: event-website::front-page
---

# Logged-in visitors see the same sponsors

## Trigger

A logged-in applicant opens the front page.

## Outcome

The same sponsor groups and logos are shown.
