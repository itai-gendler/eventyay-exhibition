---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The Organizer chooses Approve
  kind: actor
  actor: organizer
  capability: approve-exhibition-request
  entities: []
  contexts:
    web:
      place: organizer-backend::request-review
- text: The Product accepts the request and creates its organization profile, unpublished
  kind: product
  actor: organizer
  capability: approve-exhibition-request
  entities:
  - entity: exhibition-request
    effect: changes
    from: Submitted
    to: Accepted
    facts:
    - Profile at acceptance
    - Last updated
  - entity: organization-profile
    effect: creates
    to: Unpublished
    facts:
    - Name
    - Description
    - Website
    - Contact page URL
    - Video URL
    - Slides
    - Logo
    - Banner
    - Booth name
    - Social media links
    - Extra links
    - Email
    - Exhibitor
    - Sponsor
    - Sponsor group
    - Booth ID
    - Access key
    - Position
  contexts:
    web:
      place: organizer-backend::request-review
- text: The Product opens the new organization profile in its editor
  kind: product
  actor: organizer
  capability: approve-exhibition-request
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: organizer-backend::organization-editor
- text: The Organizer adds related sessions and turns on lead scanning, and saves
  kind: actor
  actor: organizer
  capability: edit-organization
  entities:
  - entity: organization-profile
    effect: changes
    facts:
    - Related sessions
    - Lead scanning
  contexts:
    web:
      place: organizer-backend::organization-editor
---

# Approve and land in the profile editor

## Trigger

An organizer chooses Approve on a submitted request's review page.

## Outcome

The organizer has completed the new profile and is back on the exhibitors list.
