---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer turns on lead scanning and saves
  kind: actor
  actor: organizer
  entities:
  - entity: organization-profile
    effect: changes
    facts:
    - Lead scanning
  contexts:
    web:
      place: organizer-backend::organization-editor
- text: The Product creates the default number of devices for a profile that has none and places the access email in the outbox
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
  - entity: queued-email
    effect: creates
    to: In outbox
    facts:
    - Kind
    - Recipient
    - Subject
    - Body
    - Language
  contexts:
    web:
      place: organizer-backend::organization-editor
---

# Turn on lead scanning

## Trigger

An organizer turns on Can scan attendee badges for an exhibitor without devices.

## Outcome

The exhibitor has devices and an access email waits in the outbox.

## Edge cases

- Turning on voucher access queues the same access email when devices await setup.
