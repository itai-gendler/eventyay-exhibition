---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer opens Exhibition overview
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::overview
- text: The Organizer reads the counts, the recent exhibition requests and the call status
  kind: actor
  actor: organizer
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Exhibitor
    - Sponsor
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
    - Exhibitor
    - Sponsor
    - Submitted at
  - entity: event
    effect: reads
    facts:
    - Call enabled
    - Private call
    - Submission deadline
    - Call open
  contexts:
    web:
      place: organizer-backend::overview
---

# Read the overview

## Trigger

An organizer opens the exhibition from the event's dashboard.

## Outcome

The organizer sees the counts, the five most recent requests and whether the call is open, closed, private or not published.
