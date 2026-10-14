---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer selects organization profiles and chooses Download access keys
  kind: actor
  actor: organizer
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: organizer-backend::organizations
- text: The Product returns a CSV of their name, booth ID, booth name, email and access key
  kind: product
  actor: organizer
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
    - Booth ID
    - Booth name
    - Email
    - Access key
  contexts:
    web:
      place: organizer-backend::organizations
---

# Download the keys

## Trigger

An organizer chooses Download exhibitor keys.

## Outcome

The organizer has a CSV of the organizations and their access keys.

## Edge cases

- With none selected, every listed organization is included.
