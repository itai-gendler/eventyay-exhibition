---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer fills in the profile with lead scanning on and saves
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
- text: The Product creates the default number of lead-scanning devices for the profile
  kind: product
  actor: organizer
  entities:
  - entity: lead-scanning-device
    effect: creates
    facts:
    - Name
    - Setup token
    - Status
    - Revoked
  - entity: event
    effect: reads
    facts:
    - Devices per profile
  contexts:
    web:
      place: organizer-backend::organization-editor
- text: The Product places the access email with the access key and each device's setup token in the outbox
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
    - Access key
    - Email
  contexts:
    web:
      place: organizer-backend::organization-editor
---

# Add an exhibitor who scans leads

## Trigger

An organizer adds an exhibitor with Can scan attendee badges turned on.

## Outcome

The exhibitor has the event's default number of devices and an email with its access key and device setup tokens waits in the outbox.

## Edge cases

- Without an email address or with 0 devices per profile, no access email is queued and the organizer is told why.
