---
kind: alternative
routes:
  api: API
steps:
- text: The Organizer sends a new sponsor with its sponsor group name to the organizer API
  kind: actor
  actor: organizer
  entities:
  - entity: sponsor-group
    effect: reads
    facts:
    - Name
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
    - Lead scanning
    - Lead access
    - Voucher access
    - Lead scanning behavior
    - Related sessions
    - Access key
    - Position
  contexts:
    api:
      place: organizer-api
- text: The Product uses the sponsor group with that name and level, or creates it at the next level on the front page
  kind: product
  actor: organizer
  entities:
  - entity: sponsor-group
    effect: creates
    facts:
    - Name
    - Level
    - Show on front page
    - Vouchers per sponsor
  contexts:
    api:
      place: organizer-api
---

# Add a profile through the organizer API

## Trigger

An integration of the organizers creates a sponsor with a sponsor group name.

## Outcome

The profile exists; a sponsor group of that name is used, or created and shown on the front page.

## Edge cases

- A name matching several groups needs a level; a level that matches none of the named groups is refused.
- A profile that is not an exhibitor has no booth and no lead scanning or voucher access.
