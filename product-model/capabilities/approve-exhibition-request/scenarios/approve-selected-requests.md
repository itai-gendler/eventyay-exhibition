---
kind: alternative
routes:
  web: Web
steps:
- text: The Request manager selects requests and chooses Approve selected, then confirms
  kind: actor
  actor: request-manager
  entities: []
  contexts:
    web:
      place: organizer-backend::requests
- text: The Product approves every selected request that is submitted or rejected
  kind: product
  actor: request-manager
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
      place: organizer-backend::requests
- text: The Product places an acceptance email for each approved request in the outbox
  kind: product
  actor: request-manager
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
  contexts:
    web:
      place: organizer-backend::requests
- text: The Product reports how many were approved and how many were skipped because they were already processed
  kind: product
  actor: request-manager
  entities: []
  contexts:
    web:
      place: organizer-backend::requests
---

# Approve several requests at once

## Trigger

A request manager selects requests in the list, or every request matching the filters across pages, and chooses Approve selected.

## Outcome

Each request that can still be approved is accepted with its profile and acceptance email; the others are skipped and counted.
