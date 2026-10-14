---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Generate new setup tokens and confirms
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::organization-devices
- text: The Product gives each device a new token and disconnects those that were set up, saying how many
  kind: product
  actor: organizer
  entities:
  - entity: lead-scanning-device
    effect: changes
    facts:
    - Setup token
    - Status
    - Revoked
  contexts:
    web:
      place: organizer-backend::organization-devices
- text: The Product places the access email with the new tokens in the outbox when the exhibitor scans leads
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
    - Lead scanning
    - Email
  contexts:
    web:
      place: organizer-backend::organization-devices
---

# Generate new tokens

## Trigger

A device was lost and an organizer chooses Generate new setup tokens.

## Outcome

Every device of the exhibitor awaits setup with a new token; a new access email waits in the outbox.
