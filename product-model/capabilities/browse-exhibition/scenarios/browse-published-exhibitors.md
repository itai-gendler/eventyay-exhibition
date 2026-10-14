---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor opens the Exhibition tab
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: event-website::exhibition
- text: The Product lists the published, active exhibiting profiles that have a logo and a banner, in their set order
  kind: product
  actor: visitor
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
    - Logo
    - Banner
    - Exhibitor
    - Position
  contexts:
    web:
      place: event-website::exhibition
- text: The Visitor reads the names, logos and banners of the listed organization profiles
  kind: actor
  actor: visitor
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
    - Logo
    - Banner
  contexts:
    web:
      place: event-website::exhibition
---

# Browse the published exhibitors

## Trigger

A visitor opens the Exhibition tab of an event website.

## Outcome

The visitor sees each published exhibitor's logo, banner and name, and can open its page.

## Edge cases

- When no exhibitor is published, the page says no exhibitors are currently available and the tab is not shown in the website's header.
