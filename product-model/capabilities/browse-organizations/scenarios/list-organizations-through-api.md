---
kind: alternative
routes:
  api: API
steps:
- text: The Organizer asks the organizer API for the exhibitors
  kind: actor
  actor: organizer
  entities: []
  contexts:
    api:
      place: organizer-api
- text: The Product returns each organization profile with its details, sponsor group and links
  kind: product
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
    - Booth name
    - Social media links
    - Extra links
    - Email
    - Access key
    - Exhibitor
    - Sponsor
    - Sponsor group
    - Booth ID
    - Lead scanning
    - Lead access
    - Voucher access
    - Lead scanning behavior
    - Related sessions
  - entity: sponsor-group
    effect: reads
    facts:
    - Name
    - Level
  contexts:
    api:
      place: organizer-api
---

# List the profiles through the organizer API

## Trigger

An integration of the organizers reads the event's exhibitors.

## Outcome

The integration receives every profile with its links, sponsor group name and level.
