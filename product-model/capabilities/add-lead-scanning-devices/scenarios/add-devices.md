---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer reads the provisioned devices and their status
  kind: actor
  actor: organizer
  entities:
  - entity: lead-scanning-device
    effect: reads
    facts:
    - Name
    - Status
    - Setup token
  contexts:
    web:
      place: organizer-backend::organization-devices
- text: The Organizer enters how many devices to add and chooses Add devices
  kind: actor
  actor: organizer
  entities:
  - entity: lead-scanning-device
    effect: creates
    facts:
    - Name
    - Setup token
    - Status
    - Revoked
  contexts:
    web:
      place: organizer-backend::organization-devices
- text: The Product places the access email with the setup token of each device awaiting setup in the outbox
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
    - Access key
    - Email
  contexts:
    web:
      place: organizer-backend::organization-devices
---

# Add devices

## Trigger

An organizer opens an exhibitor's Lead-scanning devices and adds two.

## Outcome

The exhibitor has two more devices awaiting setup and the access email waits in the outbox.

## Edge cases

- Between 1 and 50 devices can be added at a time.
- No access email is queued for an exhibitor without lead scanning or without an email address.
