---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor opens the front page
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: event-website::front-page
- text: The Product lists the sponsor groups shown on the front page that have at least one published, active sponsor with a logo, by level
  kind: product
  actor: visitor
  entities:
  - entity: sponsor-group
    effect: reads
    facts:
    - Name
    - Level
    - Show on front page
  - entity: organization-profile
    effect: reads
    facts:
    - Sponsor
    - Logo
    - Position
  contexts:
    web:
      place: event-website::front-page
- text: The Visitor reads each sponsor group's name and its sponsors' logos
  kind: actor
  actor: visitor
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

# See the sponsors on the front page

## Trigger

A visitor opens the event's front page.

## Outcome

The visitor sees the chosen sponsor groups with the logos of their published sponsors.

## Edge cases

- A group with no published sponsor that has a logo is left out; with no such group, nothing is added to the front page.
