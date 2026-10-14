---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor opens one organization profile from the list
  kind: actor
  actor: visitor
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: event-website::exhibitor-page
- text: The Product shows the profile with its embedded video, slides and the related sessions that are on the published schedule
  kind: product
  actor: visitor
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
- text: The Visitor reads the organization profile and follows its Get In Touch link
  kind: actor
  actor: visitor
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

# Open a published exhibitor's page

## Trigger

A visitor chooses an exhibitor on the Exhibition page.

## Outcome

The visitor sees the exhibitor's profile, its links and its sessions, and can step to the previous or next exhibitor of the list.

## Edge cases

- When the schedule is not public, no sessions are shown.
- Previous and Next wrap around the list and keep its search and sponsor group filter; a page the filter no longer matches steps through all exhibitors.
