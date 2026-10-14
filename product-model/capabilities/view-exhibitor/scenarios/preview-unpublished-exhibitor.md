---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer opens an organization profile from the preview
  kind: actor
  actor: organizer
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: event-website::exhibitor-page
- text: The Product shows the active organization profile though it is not published, and keeps the preview on Previous and Next
  kind: product
  actor: organizer
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Video URL
    - Slides
    - Related sessions
  contexts:
    web:
      place: event-website::exhibitor-page
- text: The Organizer reads the organization profile
  kind: actor
  actor: organizer
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
    - Description
    - Website
    - Contact page URL
    - Video URL
    - Slides
    - Logo
    - Banner
    - Social media links
    - Extra links
    - Related sessions
  contexts:
    web:
      place: event-website::exhibitor-page
---

# Preview an approved exhibitor's page

## Trigger

An organizer follows an exhibitor from the preview of the Exhibition page.

## Outcome

The organizer sees the page of an approved exhibitor before it is published.
