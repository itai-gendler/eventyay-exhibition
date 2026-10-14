---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer confirms deleting the organization profile
  kind: actor
  actor: organizer
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: organizer-backend::organization-editor
- text: The Product revokes the profile's devices, deletes its unredeemed vouchers and deletes the profile
  kind: product
  actor: organizer
  entities:
  - entity: lead-scanning-device
    effect: changes
    facts:
    - Revoked
  - entity: organization-profile
    effect: removes
    from: Unpublished
  - entity: voucher
    effect: removes
    with: organization-profile
  contexts:
    web:
      place: organizer-backend::organization-editor
---

# Delete a profile

## Trigger

An organizer deletes an exhibitor that will not attend.

## Outcome

The profile is gone, its unredeemed codes deleted and its devices can no longer scan.
