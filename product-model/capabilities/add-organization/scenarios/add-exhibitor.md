---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer fills in the exhibitor's profile, email and booth and saves
  kind: actor
  actor: organizer
  entities:
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
    web:
      place: organizer-backend::organization-editor
- text: The Product generates a booth ID if none was given, unique among the booths
  kind: product
  actor: organizer
  entities:
  - entity: organization-profile
    effect: changes
    facts:
    - Booth ID
  contexts:
    web:
      place: organizer-backend::organization-editor
- text: The Product places the invitation to complete the profile in My Exhibitions in the outbox
  kind: product
  actor: organizer
  entities:
  - entity: queued-email
    effect: creates
    to: In outbox
    facts:
    - Kind
    - Recipient
    - Subject
    - Body
    - Language
  - entity: organization-profile
    effect: reads
    facts:
    - Name
    - Email
  contexts:
    web:
      place: organizer-backend::organization-editor
- text: The Product shows the exhibitors list
  kind: product
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organizations
---

# Add an exhibitor

## Trigger

An organizer chooses Add an Exhibitor.

## Outcome

The exhibitor exists, unpublished unless the organizer chose to show it, and an invitation to edit its profile waits in the outbox.

## Edge cases

- A sponsor-only profile, or one without an email, gets no invitation.
- Ticking Show on the public event website adds it as published.
