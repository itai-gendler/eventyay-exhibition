---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer opens the public page in preview
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: event-website::exhibition
- text: The Organizer may change the settings
  kind: condition
  actor: organizer
  entities: []
  contexts:
    web:
      place: event-website::exhibition
- text: The Product lists every active exhibiting organization profile with a logo and a banner, published or not, and keeps the preview on links to their pages
  kind: product
  actor: organizer
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
    - Logo
    - Banner
    - Exhibitor
  contexts:
    web:
      place: event-website::exhibition
- text: The Organizer reads the previewed organization profiles
  kind: actor
  actor: organizer
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

# Preview the exhibition before publishing

## Trigger

An organizer chooses Preview public page on the exhibitors list.

## Outcome

The organizer sees the page as it will look once every approved exhibitor is published; visitors still see only the published ones.

## Edge cases

- Someone who may not change the event's settings who asks for the preview sees only the published exhibitors.
