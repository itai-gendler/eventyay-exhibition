---
kind: validation
routes:
  web: Web
steps:
- text: The Applicant opens the page of an organization profile
  kind: actor
  actor: applicant
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: event-website::exhibitor-page
- text: The organization profile is not published, is inactive, or lacks a logo or banner
  kind: condition
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Logo
    - Banner
  contexts:
    web:
      place: event-website::exhibitor-page
- text: The Product answers that the page does not exist
  kind: product
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::exhibitor-page
---

# An unpublished exhibitor's page stays hidden

## Trigger

A logged-in applicant opens the address of an organization profile that is not published.

## Outcome

The page is not found; nothing about the profile is shown.
